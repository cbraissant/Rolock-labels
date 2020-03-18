<script>
  import { labelsToPrint } from "./stores.js";

  let indexSelectedProduct;
  let productQuantity = 0;
  let newLabelsToPrint;

  const subscribe = labelsToPrint.subscribe(value => {
    newLabelsToPrint = value;
  });

  function setValue() {
    newLabelsToPrint[indexSelectedProduct].product_quantity = productQuantity;
    labelsToPrint.set(newLabelsToPrint);
  }
</script>

<style>
  div {
    padding: 10px 0;
    display: flex;
  }
</style>

<div>
  <select class="product-select" name="item" bind:value={indexSelectedProduct}>
    {#each newLabelsToPrint as singleArticle, i}
      <option value={i}>{singleArticle.product_model}</option>
    {/each}
  </select>
  <input type="number" min="0" bind:value={productQuantity} />
  <button on:click={setValue}>SET</button>
</div>
