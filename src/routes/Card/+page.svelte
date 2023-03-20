<script lang="ts">
	let cardNumber = '';
	const cardNumberPlaceholder = '1234 0000 0000 0000';
	let name = '';
	const namePlaceholder = 'Samu Sammakko';
	let expMonth = '';
	const expMonthPlaceholder = '10';
	let expYear = '';
	const expYearPlaceholder = '23';
	let cvc = '';
	const cvcPlaceholder = '000';

	const lengthCheck = (value: String, placeholder: String) =>
		value.length === 0 ? placeholder : value;
</script>

<main>
	<div class="grid">
		<section class="cards">
			<div class="card front">
				<div class="card-front-data">
					<div class="balls">
						<span class="circle-filled" />
						<span class="circle" />
					</div>
					<p class="number">{lengthCheck(cardNumber, cardNumberPlaceholder)}</p>
					<div class="name-exp">
						<p class="name">{lengthCheck(name, namePlaceholder)}</p>
						<p class="exp">
							{`${lengthCheck(expMonth, expMonthPlaceholder)}/${lengthCheck(
								expYear,
								expYearPlaceholder
							)}`}
						</p>
					</div>
				</div>
			</div>
			<div class="right">
				<div class="card back right">
					<div class="card-back-data">
						<p>{lengthCheck(cvc, cvcPlaceholder)}</p>
					</div>
				</div>
			</div>
		</section>
		<section class="form">
			<label for="cardholderName">
				CARDHOLDER NAME
				<input type="text" name="cardholderName" placeholder={namePlaceholder} bind:value={name} />
			</label>
			<label for="cardNumber">
				CARD NUMBER
				<input
					type="text"
					name="cardNumber"
					placeholder={cardNumberPlaceholder}
					bind:value={cardNumber}
				/>
			</label>
			<div class="exp-cvc">
				<label for="exp-dates" class="exp">
					EXP.DATE (MM/YY)
					<div class="exp-dates">
						<input
							type="text"
							placeholder={expMonthPlaceholder}
							name="expMM"
							class="input-small"
							bind:value={expMonth}
						/>
						<input
							type="text"
							placeholder={expYearPlaceholder}
							name="expYY"
							class="input-small"
							bind:value={expYear}
						/>
					</div>
				</label>
				<label for="cvc">
					CVC
					<input type="text" name="cvc" placeholder={cvcPlaceholder} bind:value={cvc} />
				</label>
			</div>
			<button type="submit">Confirm</button>
		</section>
	</div>
</main>

<style>
	main {
		--linear-gradient-from: hsl(249, 99%, 64%);
		--linear-gradient-to: hsl(278, 94%, 30%);
		--input-error: hsl(0, 100%, 66%);
		--white: hsl(0, 0%, 100%);
		--light-grayish-violet: hsl(270, 3%, 87%);
		--dark-grayish-violet: hsl(279, 6%, 55%);
		--very-dark-violet: hsl(278, 68%, 11%);
		/* Close enough for nows*/
		background: linear-gradient(0deg, var(--white) 66%, var(--very-dark-violet) 33%);
		font-size: 18px;
		height: 100%;
		color: var(--white);
		font-family: 'Space Grotesk';
		font-weight: 500;
	}

	.grid {
		height: 100%;
		max-width: 90vw;
		margin: auto;
		place-content: center;
	}
	@media only screen and (min-width: 600px) {
		main {
			background: linear-gradient(90deg, var(--very-dark-violet) 33%, white 33%);
		}
		.grid {
			max-width: 1024px;
			display: grid;
			grid-template-columns: 3fr 2fr;
			gap: 4em;
		}
	}
	section.cards {
		width: 100%;
		display: grid;
		row-gap: 2em;
	}

	section.form {
		display: flex;
		flex-direction: column;
		justify-content: center;
		gap: 1em;
	}

	label {
		color: var(--very-dark-violet);
		font-size: small;
		display: grid;
		place-items: left;
		row-gap: 0.5em;
		width: 100%;
	}
	label.exp {
		display: grid;
	}

	.exp-dates {
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 1em;
	}

	.exp-cvc {
		width: 100%;
		display: grid;
		grid-template-columns: 1fr 1fr;
		gap: 1em;
	}

	input {
		height: 3em;
		background-color: inherit;
		border-radius: 0.5em;
		padding: 0 1em;
		font-family: 'Space Grotesk';
		border: 1px solid var(--light-grayish-violet);
		color: var(--dark-grayish-violet);
	}

	input::placeholder {
		color: var(--light-grayish-violet);
	}

	input.input-small {
		max-width: 4em;
	}

	button {
		width: 100%;
		height: 4em;
		font-family: 'Space Grotesk';
		color: var(--white);
		background-color: var(--very-dark-violet);
		border: 1px solid black;
		border-radius: 0.5em;
	}

	.card {
		width: clamp(220px, 447px, 447px);
		height: clamp(112px, 245px, 245px);
	}

	.card.front {
		background-image: url('/card-component/bg-card-front.png');
		display: grid;
		place-items: center;
	}
	.right {
		float: right;
	}
	.card.back {
		background-image: url('/card-component/bg-card-back.png');
	}

	.card-back-data {
		height: 100%;
		width: 90%;
		display: flex;
		justify-content: end;
		align-items: center;
	}

	.card-front-data {
		height: 90%;
		width: 85%;
		display: grid;
		grid-template-rows: 2fr 1fr 1fr;
	}

	.circle-filled {
		height: 2.5em;
		width: 2.5em;
		border-radius: 50%;
		background-color: var(--white);
		display: inline-block;
	}

	.circle {
		height: 1em;
		width: 1em;
		border-radius: 50%;
		border: 1px solid white;
		display: inline-block;
	}

	.balls {
		display: flex;
		align-items: center;
		gap: 0.5em;
	}

	.name-exp {
		display: flex;
		justify-content: space-between;
		font-size: small;
		align-items: end;
	}

	.number {
		font-size: xx-large;
		display: flex;
		margin: 0;
		align-items: end;
	}
</style>
