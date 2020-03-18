<script>
  export let rolockArticles;
  import ProductCount from "./ProductCount.svelte";
  function handlePrint() {
    window.print();
    return false;
  }
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
  {#each rolockArticles as singleArticle, index}
    {#if singleArticle.product_quantity > 0}
      <ProductCount on:message {singleArticle} {index} />
    {/if}
  {/each}
</div>
