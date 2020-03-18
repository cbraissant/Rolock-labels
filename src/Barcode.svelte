<script>
  export let product_code;
  export let product_model;
  export let product_label_1;
  export let product_label_2;
  export let product_quantity;
  let link =
    `http://barcodes4.me/barcode/c39/` +
    product_code +
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
    <h2 class="product-model">{product_model}</h2>
    <p class="product-label">{product_label_1}</p>
    <p class="product-label">{product_label_2}</p>
  </div>

  <div class="product-barcode">
    <img class="barcode-image" src={link} alt="" />
    <p class="barcode-number">{product_code}</p>
  </div>
</div>
