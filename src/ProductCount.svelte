<script>
  import { labelsToPrint } from "./stores.js";
  export let index;

  let newLabelsToPrint;

  const subscribe = labelsToPrint.subscribe(value => {
    newLabelsToPrint = value;
  });

  let articleQuantity = newLabelsToPrint[index].product_quantity;

  function setValue() {
    newLabelsToPrint[index].product_quantity = articleQuantity;
    labelsToPrint.set(newLabelsToPrint);
  }

  function resetValue() {
    newLabelsToPrint[index].product_quantity = 0;
    labelsToPrint.set(newLabelsToPrint);
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
  <div class="product-model">{newLabelsToPrint[index].product_model}</div>
  <input type="number" min="0" bind:value={articleQuantity} />
  <button on:click={setValue}>SET</button>
  <button on:click={resetValue}>X</button>
</div>
