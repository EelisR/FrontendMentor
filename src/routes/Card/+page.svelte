<main>
  <div class="grid">
    <section class="cards">
      <div class="card front"> 
        
      </div>
      <div class="right">
        <div class="card back right">
          
        </div>
      </div>
    </section>
    <section class="form">
        <label for="cardholderName">
          CARDHOLDER NAME
          <input type="text" name="cardholderName" placeholder="e.g. Samu Sammakko">
        </label>
        <label for="cardNumber">
          CARD NUMBER
          <input type="text" name="cardNumber" placeholder="e.g. 1234 0000 0000 0000">
        </label>
        <div class="exp-cvc">
          <label for="exp-dates" class="exp">
            EXP.DATE (MM/YY)
            <div class="exp-dates">
              <input type="text" placeholder="MM" name="expMM" class="input-small">
              <input type="text" placeholder="YY" name="expYY" class="input-small">
            </div>
          </label>
          <label for="cvc">
            CVC
            <input type="text" name="cvc" placeholder="e.g. 123">
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
    background: linear-gradient(0deg, var(--white) 66%, var(--very-dark-violet) 33% );
    font-size: 18px;
    height: 100%;
    font-family: 'Space Grotesk';
  }
  
  .grid {
    height: 100%;
    max-width: 90vw;
    margin: auto;
    place-content: center;
  }
  @media only screen and (min-width: 600px){
    main {  
      background: linear-gradient(90deg, var(--very-dark-violet) 33%, white 33% );
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
    row-gap: .5em;
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
    border-radius: .5em;
    padding: 0 1em;
    font-family: 'Space Grotesk';
    border: 1px solid var(--light-grayish-violet);
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
    border-radius: .5em;
  }

  .card {
    width: clamp(220px, 447px, 447px);
    height: clamp(112px, 245px, 245px);
  }

  .card.front {
    background-image: url('/bg-card-front.png');
  }
  .right {
    float: right;
  }
  .card.back {
    background-image: url('/bg-card-back.png');
  }

</style>