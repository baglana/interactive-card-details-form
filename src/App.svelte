<script lang="ts">
  let name = '';
  let number = '';
  let month = 1;
  let year = 24;
</script>

0000 0000 0000 0000
Jane Appleseed
00/00

000

<form>
  <div>
    <label for="name">Cardholder Name</label>
    <input type="text" name="name" id="name"/>e.g. Jane Appleseed
  </div>
  <div>
    <label for="number">Card Number</label>
    <input type="text" name="number" id="number"/>e.g. 1234 5678 9123 0000
  </div>
  <div>
    <label for="date">Exp. Date (MM/YY)</label>
    <input type="number" name="month" id="month"/>MM
    <input type="number" name="year" id="year"/>YY
  </div>
  <div>
    <label for="cvc">CVC</label>
    <input type="number" name="cvc" id="cvc">e.g. 123
  </div>

  Confirm

  <!-- Completed state start -->

  Thank you!
  We've added your card details
  Continue
</form>

<div class="attribution">
  Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
  Coded by <a href="#">Your Name Here</a>.
</div>
