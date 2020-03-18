<script>
  import Header from "./Header.svelte";
  import Barcode from "./Barcode.svelte";
  export let index;
</script>

<style>
  .subpage {
    display: flex;
    flex-direction: column;
    padding: 2mm 5mm;
    width: 100%;
    height: 54mm;
    justify-content: space-around;
  }
</style>

<div class="page">
  <div class="subpage">
    <Header />
    <Barcode {index} />
  </div>
</div>
