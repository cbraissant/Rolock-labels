<script>
  import rawdatas from "./data.js";
  import LabelsList from "./LabelsList.svelte";
  import Sidebar from "./Sidebar.svelte";

  let datas = rawdatas;

  function handleSummary(event) {
    let value = event.detail.value;
    let index = event.detail.index;
    datas[index].product_quantity = value;
    datas = datas;
  }
</script>

<style>
  .main {
    display: flex;
  }
</style>

<main>
  <Sidebar on:message={handleSummary} {datas} />
  <LabelsList {datas} />
</main>
