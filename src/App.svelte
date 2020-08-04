<script>
  import { labelsToPrint } from "./stores.js";
  import rolockArticles from "./rolock.js";
  import LabelsList from "./LabelsList.svelte";
  import Sidebar from "./Sidebar.svelte";

  labelsToPrint.set(rolockArticles);
</script>

<style>
  .main {
    display: flex;
  }
</style>

<main>
  <Sidebar />
  <LabelsList />
</main>
