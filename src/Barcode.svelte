<script>
  import { labelsToPrint } from "./stores.js";
  export let index;

  let newLabelsToPrint;

  const subscribe = labelsToPrint.subscribe(value => {
    newLabelsToPrint = value;
  });

  let singleArticle = newLabelsToPrint[index];

  let link =
    `http://barcodes4.me/barcode/c39/` +
    singleArticle.product_code +
    `.png?resolution=4&height=150`;
</script>

<style>
  .product-content {
    display: flex;
    justify-content: space-between;
    width: 100%;
    font-size: 8pt;
  }

  .product-model {
    margin-bottom: 1mm;
  }

  .product-label {
    font-size: 8pt;
    max-width: 150px;
  }

  .barcode-image {
    width: 4.5cm;
    max-height: 2cm;
  }
  .barcode-number {
    text-align: center;
    margin-top: -1mm;
  }
</style>

<div class="product-content">

  <div class="product-description">
    <h2 class="product-model">{singleArticle.product_model}</h2>
    <p class="product-label">{singleArticle.product_description}</p>
  </div>

  <div class="product-barcode">
    <img class="barcode-image" src={link} alt="" />
    <p class="barcode-number">{singleArticle.product_code}</p>
  </div>
</div>
