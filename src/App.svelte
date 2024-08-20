<script>
  import { onDestroy } from 'svelte';

  let now = new Date();

  const timer = setInterval(() => {
    now = new Date();
  }, 1000);

  onDestroy(() => {
    console.log(`Let's cleanup {timer}.`);
    clearInterval(timer);
  });
</script>

<div>It's {now.toLocaleString()} now.</div>
