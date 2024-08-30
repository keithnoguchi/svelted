<script>
  let n = 1;
  let stars;

  $: console.log(`n id noe ${n}.`);
  $: {
    const newStars = [];
    for (let i = 0; i < n; i++) {
      newStars.push(i % 2 === 0 ? '*' : '');
    }
    stars = newStars
  }
</script>

<div>
  {#each stars as star}{star}{/each}
</div>
<div>
  <button on:click={() => (n -= 1)} disabled={n <= 1}>
    -
  </button>
  <button on:click={() => (n += 1)}>
    +
  </button>
</div>
