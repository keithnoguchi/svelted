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
      <img src="https://github.com/svelte-book/sample-app/raw/main/static/svelte-book-1.png" alt="The Cover of Svelte Guide"
      />
    </div>
  </div>
</article>

<style>
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
