<script>
  import { createEventDispatcher } from "svelte";
  export let rolockArticles;

  const dispatch = createEventDispatcher();

  let selectedProduct;
  let productQuantity = 0;
  function setValue() {
    dispatch("message", {
      value: productQuantity,
      index: selectedProduct
    });
  }
</script>

<style>
  div {
    padding: 10px 0;
    display: flex;
  }
</style>

<div>
  <select class="product-select" name="item" bind:value={selectedProduct}>
    {#each rolockArticles as singleArticle, i}
      <option value={i}>{singleArticle.product_model}</option>
    {/each}
  </select>
  <input type="number" min="0" bind:value={productQuantity} />
  <button on:click={setValue}>SET</button>
</div>
