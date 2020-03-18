<script>
  import { labelsToPrint } from "./stores.js";
  import ProductCount from "./ProductCount.svelte";

  function handlePrint() {
    window.print();
    return false;
  }

  let newLabelsToPrint;

  const subscribe = labelsToPrint.subscribe(value => {
    newLabelsToPrint = value;
  });
</script>

<style>
  p {
    margin-top: 40px;
    text-align: center;
    text-transform: uppercase;
  }
  button {
    display: block;
    margin: 10px auto;
    width: 50%;
  }
</style>

<div>
  <p>Label to print</p>
  <button on:click={handlePrint}>PRINT</button>
  {#each newLabelsToPrint as singleArticle, index}
    {#if singleArticle.product_quantity > 0}
      <ProductCount {index} />
    {/if}
  {/each}
</div>
