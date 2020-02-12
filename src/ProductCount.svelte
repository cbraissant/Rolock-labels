<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let data;
  export let index;

  function setValue() {
    dispatch("message", {
      value: data.product_quantity,
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
  <div class="product-model">{data.product_model}</div>
  <input type="number" bind:value={data.product_quantity} />
  <button on:click={setValue}>SET</button>
  <button on:click={resetValue}>X</button>
</div>
