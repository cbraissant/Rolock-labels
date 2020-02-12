<script>
  export let datas;
  import Label from "./Label.svelte";
</script>

<div class="book">
  {#each datas as data}
      {#each Array(data.product_quantity) as qte, i}
        <Label {data} />
      {/each}
  {/each}
</div>
