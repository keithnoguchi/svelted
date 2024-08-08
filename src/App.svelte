<script>
  let name = 'Svelted';
  let src =
    'https://github.com/sveltejs/branding/raw/master/svelte-logo.png';
  let alt = "Svelte's logo";
</script>

<p class="text">Hello, {name}!</p>
<img {src} {alt} class="logo" >

<div>It's {new Date()} now.</div>

<style>
  .logo {height: 6em;}
</style>
