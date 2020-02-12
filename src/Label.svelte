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

<div class="page">
  <div class="subpage">

    <div class="header">
      <div class="main-logo">
        <img
          class="logo-rolock"
          src="./assets/rolock_logo_side_bw.png"
          alt="" />
        <p class="main-text">
          documentation, user guide and video tutorials on our website:
          <strong>www.rolock.ch</strong>
        </p>
      </div>

      <img class="qrcode" src="./assets/rolock_qrcode.png" alt="" />
    </div>

    <div class="content">
      <div class="product-description">
        <h2 class="model">{product_model}</h2>
        <p>{product_label_1}</p>
        <p>{product_label_2}</p>
      </div>
      <div class="product-barcode">
        <img class="barcode" src={link} alt="" />
        <p class="barcode-number">{product_code}</p>
      </div>
    </div>

  </div>
</div>
