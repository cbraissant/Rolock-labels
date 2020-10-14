<script>
  import { labelsToPrint } from "./stores.js";
  import rolockArticles from "./rolock.js";
  import LabelsList from "./LabelsList.svelte";
  import Sidebar from "./Sidebar.svelte";

  labelsToPrint.set(rolockArticles);
</script>

<style>
  main {
    display: flex;
    height: 100%;
    width: 100%;
  }
</style>

<main>
  <Sidebar />
  <LabelsList />
</main>
