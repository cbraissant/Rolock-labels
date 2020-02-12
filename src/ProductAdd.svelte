<script>
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let datas;
  let selected;
  let quantity = 0;
  function setValue() {
    dispatch("message", {
      value: quantity,
      index: selected
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
  <select class="product-select" name="item" bind:value={selected}>
    {#each datas as data, i}
      <option value={i}>{data.product_model}</option>
    {/each}
  </select>
  <input type="number" bind:value={quantity} />
  <button on:click={setValue}>SET</button>
</div>
