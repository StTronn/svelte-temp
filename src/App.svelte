<script>
  import PaymentScript from './lib/payment_script.svelte' 
  let prices = [30, 55, 100];
  let activeIndex = 1;
  const onClick = (index) => {
    activeIndex = index;
  };

 //get all data-cartl-payment-id
 //forEach => 
  //add onClick => setShowPopup to true && passing id as parameter 
  //
  
</script>

<!-- <head>
  <link href="https://fonts.googleapis.com/css?family=Bentham|Playfair+Display|Raleway:400,500|Suranna|Trocchi" rel="stylesheet">
</head> -->

<div data-tip="tanisha" />
<div class="wrapper-card">
  <!-- <div class="product-img">
    <img
      alt="product-desc-tipping"
      src="http://bit.ly/2tMBBTd"
      height="480"
      width="347"
    />
  </div> -->
  <div class="product-info">
    <div class="product-text">
      <h1>Ka-ching</h1>
      <h2>by Tanisha</h2>
      <p>
        Everything about digital payments, products, processes and stakeholders<br
        />
        that collaboratively are working for a <br/> digitally  and financially enabled
        India<br />
      </p>
      <div class="product-price-btn buy-now-wrapper">
        <div class="amount-wrapper">
          {#each prices as price, i}
            <div
              on:click={() => onClick(i)}
              class={`round-button ${
                activeIndex === i ? "selected-button" : ""
              }`}
            >
              {price+"$"}
            </div>
          {/each}
        </div>
        <div data-cartl-payment-button='asfjdmv19vm'>Test Button</div>
        <button type="button">buy now</button>
      </div>
    </div>
  </div>
<PaymentScript/>
</div>

<style>
  /* 
* Design by Robert Mayer:https://goo.gl/CJ7yC8
*
*I intentionally left out the line that was supposed to be below the subheader simply because I don't like how it looks.
*
* Chronicle Display Roman font was substituted for similar fonts from Google Fonts.
*/

  .wrapper-card {
    height: 480px;
  }
  .product-img {
    float: left;
    width: 327px;
    height: 480px;
  }

  .product-img img {
    border-radius: 7px 0 0 7px;
  }

  .product-info {
    float: left;
    width: 327px;
    height: 480px;
    border-radius: 0 7px 10px 7px;
    background-color: #f9fafb;
  }

  .product-text {
    height: 300px;
    width: 327px;
  }

  .product-text h1 {
    margin: 0 0 0 38px;
    padding-top: 52px;
    font-size: 34px;
    color: #474747;
  }

  .buy-now-wrapper {
    display: grid;
    place-items: center;
  }
  .amount-wrapper {
    display: flex;
  }
  .product-text h1,
  .product-price-btn div {
    /* font-family: "Bentham", serif; */
  }

  .product-text h2 {
    margin: 0 0 47px 38px;
    font-size: 13px;
    /* font-family: "Raleway", sans-serif; */
    font-weight: 400;
    text-transform: uppercase;
    color: #d2d2d2;
    letter-spacing: 0.2em;
  }

  .product-text p {
    height: 125px;
    margin: 0 0 0 38px;
    /* font-family: "Playfair Display", serif; */
    color: #8d8d8d;
    line-height: 1.7em;
    font-size: 15px;
    font-weight: lighter;
    overflow: hidden;
  }

  .product-price-btn {
    height: 103px;
    width: 327px;
    margin-top: 17px;
    position: relative;
  }

  .product-price-btn div {
    /* font-family: "Trocchi", serif; */
    margin: 0 12px 14px 12px;
    /* font-weight: lighter; */
    /* font-size: 13px; */
    color: #474747;
  }
  .selected-button {
    color: #ffffff;
    background-color: #fecaca;
    border: 0 none;
  }

  .round-button {
    display: flex;
    margin-right: 0.5rem;
    /* background-color: #fecaca; */
    border: 2px #fecaca solid;
    justify-content: center;
    align-items: center;
    width: 3.2rem;
    height: 3.2rem;
    border-radius: 3.8rem;
    cursor: pointer;
    font-size: 14px;
    line-height: 2rem;
    font-weight: 600;
  }
  /* .round-button {
    width: 62px;
    height: 62px;
    line-height: 62px;
    display: block;
    position: relative;
    -moz-border-radius: 50%;
    -webkit-border-radius: 50%;
    border-radius: 50%;
    border: 2px solid #444;
    text-align: center;
    display: inline-block;
    vertical-align: middle;
    position: relative;
    z-index: 10;
    color: #333;
  } */
  .product-price-btn button {
    float: right;
    display: inline-block;
    height: 50px;
    width: 210px;
    /* margin: 0 40px 0 16px; */
    box-sizing: border-box;
    border: transparent;
    border-radius: 8px;
    /* font-family: "Raleway", sans-serif; */
    font-size: 14px;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.2em;
    color: #ffffff;
    background-color: #f87171;
    cursor: pointer;
    outline: none;
  }

  .product-price-btn button:hover {
    background-color: #fecaca;
  }
</style>
