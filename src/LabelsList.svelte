<script>
  export let rolockArticles;
  import Label from "./Label.svelte";
</script>

<div class="book">
  {#each rolockArticles as singleArticle}
    {#each Array(singleArticle.product_quantity) as qte, i}
      <Label {singleArticle} />
    {/each}
  {/each}
</div>
