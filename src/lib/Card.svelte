<script>
  export let name;
  export let number;
  export let month;
  export let year;
  export let cvc;
</script>

<article class="front">
  <p>{number}</p>

  <span>{name}</span>

  <span>{month}/{year}</span>
</article>

<article class="back">
  <p>{cvc}</p>
</article>

<style>
  article {
      width: 27.9375rem;
      /*height: 15.3125rem;*/
      flex-shrink: 0;
      border-radius: 0.625rem;

      &.front {
          background: linear-gradient(164deg, #6348FE 4.74%, #610595 88.83%);
          color: #fff;
      }

      &.back {
          background: linear-gradient(169deg, #FFF 5%, #D2D3D9 91.69%);
          color: #000;
      }
  }
</style>