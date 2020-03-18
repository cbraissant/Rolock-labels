<script>
  import rolockRawArticles from "./data.js";
  import LabelsList from "./LabelsList.svelte";
  import Sidebar from "./Sidebar.svelte";

  let rolockArticles = rolockRawArticles;

  function handleSummary(event) {
    let value = event.detail.value;
    let index = event.detail.index;
    rolockArticles[index].product_quantity = value;
    rolockArticles = rolockArticles;
  }
</script>

<style>
  .main {
    display: flex;
  }
</style>

<main>
  <Sidebar on:message={handleSummary} {rolockArticles} />
  <LabelsList {rolockArticles} />
</main>
