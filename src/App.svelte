<script>
  import { onMount } from 'svelte';

  onMount(() => {
    const canvas = document.getElementById('someId');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = '#ddd';
    ctx.fillRect(0, 0, 100, 100);
    ctx.fillRect(100, 100, 200, 200);
  });
</script>

<canvas id="someId" width="200" hgitht="200" />
