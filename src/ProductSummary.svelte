<script>
  export let datas;
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
  {#each datas as data, index}
    {#if data.product_quantity > 0}
      <ProductCount on:message {data} {index} />
    {/if}
  {/each}
</div>
