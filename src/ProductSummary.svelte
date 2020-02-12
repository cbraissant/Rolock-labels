<script>
  export let datas;
  import ProductCount from "./ProductCount.svelte";
</script>

<style>
  p {
    margin-top: 40px;
    text-align: center;
    text-transform: uppercase;
  }
</style>

<div>
  <p>Label to be printed</p>
  {#each datas as data, index}
    {#if data.product_quantity > 0}
      <ProductCount on:message {data} {index} />
    {/if}
  {/each}
</div>
