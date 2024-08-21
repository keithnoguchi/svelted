<script>
  import { tick } from 'svelte';

  let clicked = false;

  async function handler() {
    clicked = true;

    await tick();
    const canvas = document.getElementById('canvas');
    const ctx = canvas.getContext('2d');
    ctx.fillStyle = '#ddd';
    ctx.fillRect(0, 0, 100, 200);
    ctx.fillRect(100, 100, 200, 200);
  }
</script>

<div>
  <button on:click={handler}>Display</button>
</div>

{#if clicked}
  <canvas id="canvas" width="200" height="200" />
{/if}

<style>
</style>
