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
  <script>
    let cart = [];

    function addToCart(productId) {
      cart = [...cart, productId];
    }
  </script>
</header>

<article class="product">
  <div class="product-main">
    <div class="image-container">
      <img
        src="https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-1.png"
	alt="The Cover of Svelte Guide"
      />
    </div>
    <div>
      <h2>Svelte Guide</h2>
      <dl>
        <dt>Prince</dt>
	<dd>$35</dd>
      </dl>
      <div>
        <button on:click={() => addToCart('svelte-book')}>
	  Add to cart
	</button>
      </div>
    </div>
  </div>
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
</style>
