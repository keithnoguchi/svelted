<script>
  let name = 'Svelted';
  let attrs = {
    src: 'https://github.com/sveltejs/branding/raw/master/svelte-logo.png',
    alt: "Svelte's logo",
  };
  let disabled = true;
</script>

<p class="text">
  Hello, {name}!
  It's {new Date()} now.
</p>
<img {...attrs} class="logo" >
<button {disabled}>Click it!</button>

<style>
  .logo {height: 6em;}
</style>
