<script lang="ts">
  import Card from './lib/Card.svelte';

  type Card = {
    number: string;
    name: string;
    month: string;
    year: string
    cvc: string;
  };

  let data: Card = {
    number: '0000000000000000',
    name: 'Jane Appleseed',
    month: '00',
    year: '00',
    cvc: '000'
  };

  let confirmed = false;
  
  function handleClick() {
    confirmed = true;
  }

  function handleInput(e: Event) {
    const target = e.target as HTMLInputElement;
    if (target) {
      data[target.name as keyof Card] = target.value;
    }
  }
</script>

<Card {...data}/>

{#if !confirmed}
  <form novalidate action="https://httpbin.org/post" method="post">
    <div>
      <label for="name">Cardholder Name</label>
      <input type="text" id="name" name="name" autocomplete="cc-name" placeholder="e.g. Jane Appleseed" on:input={handleInput}/>
    </div>

    <div>
      <label for="number">Card Number</label>
      <input type="text" id="number" name="number" inputmode="numeric" autocomplete="cc-number" placeholder="e.g. 1234 5678 9123 0000" maxlength="16" on:input={handleInput}/>
    </div>

    <div>
      <label>Exp. Date (MM/YY)
        <input type="number" id="month" name="month" autocomplete="cc-exp-month" placeholder="MM" min="1" max="12" on:input={handleInput}/>
        <input type="number" id="year" name="year" autocomplete="cc-exp-year" placeholder="YY" min="24" max="99" on:input={handleInput}>
      </label>
    </div>

    <div>
      <label for="cvc">CVC</label>
      <input type="password" id="cvc" name="cvc" inputmode="numeric" autocomplete="cc-csc" placeholder="e.g. 123" maxlength="3" on:input={handleInput}>
    </div>

    <div>
      <button type="submit" on:click|preventDefault={handleClick}>Confirm</button>
    </div>
  </form>
{:else}
  <!-- Completed state start -->
  <svg xmlns="http://www.w3.org/2000/svg" width="80" height="80" viewBox="0 0 80 80" fill="none">
    <circle cx="40" cy="40" r="40" fill="url(#paint0_linear_0_524)"/>
    <path d="M28 39.9199L36.0801 48L52.0801 32" stroke="white" stroke-width="3"/>
    <defs>
      <linearGradient id="paint0_linear_0_524" x1="-23.0143" y1="11.5071" x2="1.03143e-06" y2="91.5071" gradientUnits="userSpaceOnUse">
        <stop stop-color="#6348FE"/>
        <stop offset="1" stop-color="#610595"/>
      </linearGradient>
    </defs>
  </svg>
  <h1>Thank you!</h1>
  <p>We've added your card details</p>
  <button type="reset">Continue</button>
{/if}

<div class="attribution">
  Challenge by <a href="https://www.frontendmentor.io?ref=challenge" target="_blank">Frontend Mentor</a>.
  Coded by <a href="#">Your Name Here</a>.
</div>

<style>
    form {
        max-width: 23.8125rem;
        display: flex;
        flex-direction: column;
    }

    input {
        /*width: 100%;*/
        /*border-radius: 0.5rem;*/
        border: 1px solid var(--Light-Grey, #DFDEE0);
        /*background: var(--White, #FFF);*/

        &:focus {
            border: 1px solid var(--Gradient, #6348FE);
        }
        &:invalid {
            border: 1px solid var(--Red, #FF5050);
        }
  }

</style>