<script lang="ts">
  let name = '';
  let number = '';
  let month = 1;
  let year = 24;
  
  function handleClick() {
    console.log("hello");
  }
</script>

0000 0000 0000 0000
Jane Appleseed
00/00

000

<form>
  <div>
    <label for="name">Cardholder Name</label>
    <input type="text" name="name" id="name" bind:value={name}/>e.g. Jane Appleseed
  </div>
  <div>
    <label for="number">Card Number</label>
    <input type="text" name="number" id="number" bind:value={number}/>e.g. 1234 5678 9123 0000
  </div>
  <div>
    <label>Exp. Date (MM/YY)
      <input type="number" name="month" id="month" bind:value={month}/>MM
      <input type="number" name="year" id="year" bind:value={year}/>YY
    </label>
  </div>
  <div>
    <label for="cvc">CVC</label>
    <input type="number" name="cvc" id="cvc">e.g. 123
  </div>

  <div>
    <button type="button" on:click={handleClick}>Confirm</button>
  </div>


  <!-- Completed state start -->

  Thank you!
  We've added your card details
  Continue
</form>

<div class="attribution">
  Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
  Coded by <a href="#">Your Name Here</a>.
</div>
