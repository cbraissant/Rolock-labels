<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let singleArticle;
  export let index;

  function setValue() {
    dispatch("message", {
      value: singleArticle.product_quantity,
      index: index
    });
  }
  function resetValue() {
    dispatch("message", {
      value: 0,
      index: index
    });
  }
</script>

<style>
  .product-count {
    padding: 10px 0;
    display: flex;
    align-items: center;
  }
  .product-model {
    min-width: 120px;
    text-align: center;
    vertical-align: middle;
    margin: 4px 4px;
  }
</style>

<div class="product-count">
  <div class="product-model">{singleArticle.product_model}</div>
  <input type="number" bind:value={singleArticle.product_quantity} />
  <button on:click={setValue}>SET</button>
  <button on:click={resetValue}>X</button>
</div>
