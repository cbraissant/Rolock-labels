<script>
  import ProductSummary from "./ProductSummary.svelte";
  import ProductAdd from "./ProductAdd.svelte";
  import { createEventDispatcher } from "svelte";
  const dispatch = createEventDispatcher();
  export let datas;
</script>

<style>
  .sidebar-title {
    text-align: center;
    padding: 30px 0px;
  }
</style>

<div class="sidebar">
  <div class="sidebar-title">
    <h1>Rolock</h1>
  </div>
  <ProductAdd on:message {datas} />
  <ProductSummary on:message {datas} />
</div>
