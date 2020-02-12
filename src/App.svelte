<script>
  import datas from "./data.js";
  import Label from "./Label.svelte";
</script>

<main>
  <div class="book">
    {#each datas as data}
      {#each Array(data.product_quantity) as _, i}
        <Label {...data} />
      {/each}
    {/each}
  </div>
</main>
