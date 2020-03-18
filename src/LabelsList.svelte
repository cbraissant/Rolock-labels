<script>
  import { labelsToPrint } from "./stores.js";
  import Label from "./Label.svelte";

  let newLabelsToPrint;

  const subscribe = labelsToPrint.subscribe(value => {
    newLabelsToPrint = value;
  });
</script>

<div class="book">
  {#each newLabelsToPrint as singleArticle, index}
    {#each Array(singleArticle.product_quantity)}
      <Label {index} />
    {/each}
  {/each}
</div>
