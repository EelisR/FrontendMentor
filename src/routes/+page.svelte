<script>

</script>

<main>
  <section class="cards">
    <div class="card-front"> 
      <img src="%sveltekit.assets%/bg-card-front.png" alt="Card front">
    </div>
    <div class="card-back">
      <img src="%sveltekit.assets%/bg-card-back.png" alt="Card back">
    </div>
  </section>
  <section class="form">
    <form action="#" class="input-form" id="cardForm">
      <label for="cardholderName">
        CARDHOLDER NAME
        <input type="text" name="cardholderName" placeholder="e.g. Samu Sammakko" id="cardName">
      </label>
      <label for="cardNumber">
        CARD NUMBER
        <input type="text" name="cardNumber" placeholder="e.g. 1234 0000 0000 0000" id="cardNumber">
      </label>
      <div class="exp-cvc">
        <label for="expDate" class="exp">
          EXP.DATE (MM/YY)
          <div class="exp-dates">
            <input type="text" placeholder="MM" id="expMM" class="input-small">
            <input type="text" placeholder="YY" id="expYY" class="input-small">
          </div>
        </label>
        <label for="cvc">
          CVC
          <input type="text" name="cvc" placeholder="e.g. 123" id="CVC">
        </label>
      </div>
      <button type="submit">Confirm</button>
    </form>  
  </section>
  
</main>

<style>
  :global(body){
    margin: 0;
  }

  main {
    /* Close enough for nows*/
    background: linear-gradient(90deg, rgb(132, 48, 132) 33%, white 33% );
    min-height: 70svh;
    overflow: hidden;
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 10%;
  }
  section.cards {
    position: relative;
  }

  section.form {
    display: grid;
    place-items: center;
    padding: 7.5em;
  }
  form.input-form {
    display: grid;
    place-items: center;
    row-gap: 1.5em;
    width: 100%;
  }

  label {
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
    
  }

  .exp-cvc {
    width: 100%;
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 1em;
  }

  input {
    height: 4em;
    background-color: inherit;
    border-radius: .5em;
    border: 1px solid grey;
  }

  input.input-small {
    max-width: 6em;
  }

  button {
    width: 100%;
    height: 4em;
    background-color: rgb(132, 48, 132);
    border: 1px solid black;
    border-radius: .5em;
  }
</style>