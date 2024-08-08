<script>
  let name = 'Svelted';
  let value = 'only characters and white space';
</script>

<p class="text">Hello, {name}!</p>
<div>{(/^[A-Za-z ]+$/).test(value) ? 'OK' : 'NG'}</div>

<img
  src="https://github.com/sveltejs/branding/raw/master/svelte-logo.png"
  alt="Svelte's Logo"
  class="logo"
>

<div>It's {new Date()} now.</div>

<style>
  .logo {height: 6em;}
</style>
