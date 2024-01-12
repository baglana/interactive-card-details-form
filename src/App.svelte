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

<form action="https://httpbin.org/post" method="post">
  <div>
    <label for="name">Cardholder Name</label>
    <input type="text" id="name" name="name" placeholder="e.g. Jane Appleseed" bind:value={name}/>
  </div>

  <div>
    <label for="number">Card Number</label>
    <input type="text" id="number" name="number" placeholder="e.g. 1234 5678 9123 0000" bind:value={number}/>
  </div>

  <div>
    <label>Exp. Date (MM/YY)
      <input type="number" id="month" name="month" placeholder="MM" bind:value={month}/>
      <input type="number" id="year" name="year" placeholder="YY" bind:value={year}/>
    </label>
  </div>

  <div>
    <label for="cvc">CVC</label>
    <input type="number" id="cvc" name="cvc" placeholder="e.g. 123">
  </div>

  <div>
    <button type="submit" on:click|preventDefault={handleClick}>Confirm</button>
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
