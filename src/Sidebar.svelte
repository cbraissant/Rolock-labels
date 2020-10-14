<script>
  import ProductSummary from "./ProductSummary.svelte";
  import ProductAdd from "./ProductAdd.svelte";
</script>

<style>
  h1 {
    text-align: center;
    padding: 30px 0px;
  }

  aside {
    height: 100%;
    width: 500px;
    padding: 0 20px;
    background-color: #eceff1;
  }
</style>

<aside class="sidebar">
  <h1>Rolock</h1>
  <ProductAdd />
  <ProductSummary />
</aside>
