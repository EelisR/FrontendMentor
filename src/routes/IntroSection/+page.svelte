<div class="intro-section">
	<nav>
		<span class="navbar-logo">
			<img src="/intro-section/logo.svg" alt="Logo of the site" />
		</span>
		<div class="navbar-links">
			<a href="http://" target="_blank" rel="noopener noreferrer">Features</a>
			<a href="http://" target="_blank" rel="noopener noreferrer">Company</a>
			<a href="http://" target="_blank" rel="noopener noreferrer">Careers</a>
			<a href="http://" target="_blank" rel="noopener noreferrer">About</a>
		</div>
		<div class="navbar-right">
			<a href="http://" class="login">Login</a>
			<a href="http://" class="register">Register</a>
		</div>
	</nav>
</div>

<style>
	.intro-section {
		--almost-white: hsl(0, 0%, 98%);
		--medium-gray: hsl(0, 0%, 41%);
		--almost-black: hsl(0, 0%, 8%);
		background-color: var(--almost-white);
		min-height: 100%;
		color: var(--medium-gray);
		font-size: 18px;
		font-family: 'Epilogue';
	}

	nav {
		display: flex;
		justify-content: space-between;
		gap: 3em;
		padding: 2em;
		align-items: center;
	}

	.navbar-links {
		display: inherit;
		width: 100%;
		gap: 2em;
		color: var(--medium-gray);
	}

	a {
		color: inherit;
		text-decoration: none;
	}

	.navbar-right {
		display: inherit;
		align-items: center;
		gap: 2em;
	}

	a.register {
		font-size: inherit;
		color: inherit;
		background-color: inherit;
		border: 2px solid var(--medium-gray);
		border-radius: 0.75em;
		padding: 0.75em;
	}
</style>
