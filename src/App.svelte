<script>
  let product = {
    id: 'svelte-book',
    name: 'Svelte Book',
    price: 35,
    images: [
      'https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-1.png',
      'https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-2.png',
      'https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-3.png',
    ],
  };
  const relatedProducts = [
    {
      id: 'react-book',
      name: 'React Book',
      prince: 35,
    },
    {
      id: 'vue-book',
      name: 'Vue Book',
      prince: 35,
    },
    {
      id: 'angular-book',
      name: 'Angular Book',
      prince: 35,
    },
  ];
  let cart = [];

  function addToCart(productId) {
    cart = [...cart, productId];
  }

  // For the image slider.
  let sliderCenterIndex = 0;
  let sliderLeftIndex = product.images.length - 1;
  let sliderRightIndex = 1;

  function sliderMoveLeft() {
    const length = product.images.length;
    sliderCenterIndex = (sliderCenterIndex - 1 + length) % length;
    sliderLeftIndex = (sliderCenterIndex - 1 + length) % length;
    sliderRightIndex = (sliderCenterIndex + 1) % length;
  }

  function sliderMoveRight() {
    const length = product.images.length;
    sliderCenterIndex = (sliderCenterIndex + 1) % length;
    sliderLeftIndex = (sliderCenterIndex - 1 + length) % length;
    sliderRightIndex = (sliderCenterIndex + 1) % length;
  }
</script>

<header class="header">
  <a class="header-title" href="/">Svelted EC</a>
  <nav>
    <ul class="header-links">
      <li>Welcome</li>
      <li>
        <a href="/cart">Cart (0)</a>
      </li>
    </ul>
  </nav>
</header>

<article class="product">
  <div class="product-main">
    <div class="image-container">
      <div class="slider">
        <img
          src={product.images[sliderLeftIndex]}
          alt="The left slider image"
          class="slider-item left"
        />
        <img
          src={product.images[sliderCenterIndex]}
          alt="The center slider image"
          class="slider-item"
        />
        <img
          src={product.images[sliderRightIndex]}
          alt="The right slider image"
          class="slider-item right"
        />
        <button class="slider-left-button" on:click={sliderMoveLeft}>
          &lt
        </button>
        <button class="slider-right-button" on:click={sliderMoveRight}>
          &gt
        </button>
      </div>
    </div>
    <div>
      <h2>{product.name}</h2>
      <dl>
        <dt>price</dt>
        <dd>${product.price}</dd>
      </dl>
      <div>
        {#if !cart.includes(product.id)}
          <button on:click={() => addToCart(product.id)}>
            Add to cart
          </button>
        {/if}
      </div>
    </div>
  </div>

  <footer>
    <h3>Related Products</h3>
    <ul>
    {#each relatedProducts as product}
      <li>
        <a href="/products/{product.id}">{product.name}</a> - ${product.prince}
      </li>
    {/each}
    </ul>
  </footer>
</article>

<style>
:global(body) {
  margin: 0;
  background-color: #eee;
  padding: 0;
}

.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0 auto;
  background-color: #fff;
  padding: 0 15px;
  width: 100%;
  max-width: 800px;
  height: 50px;
}

.header-title {
  font-weight: bold;
}

.header-links {
  display: flex;
  gap: 10px;
  margin: 0;
  padding: 0;
  list-style: none;
}

.product {
  margin: 0 auto;
  background-color: #fff;
  padding: 15px;
  width: 100%;
  max-width: 800px;
}

.product-main {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}

.image-container {
  width: 100%;
  max-width: 400px;
  overflow: hidden;
}

.image-container img {
  width: 100%;
}

.slider {
  position: relative;
  width: 80%;
  margin: 0 10%;
}

.slider-item {
  width: 100%;
}

.slider-item.left {
  position: absolute;
  top: 0;
  right: 100%;
}

.slider-item.right {
  position: absolute;
  top: 0;
  left: 100%;
}

.slider-left-button {
  position: absolute;
  top: 50%;
  right: 100%;
}

.slider-right-button {
  position: absolute;
  top: 50%;
  left: 100%;
}
</style>
