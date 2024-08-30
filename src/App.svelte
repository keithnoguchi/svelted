<script>
  let x = 1;

  $: area = x * x;
  $: volume = x * x * x;
</script>

<div>
  Length:
  <button on:click={() => (x -= 1)} disabled={x <= 1}>
    -
  </button>
  {x}m
  <button on:click={() => (x += 1)}>
    +
  </button>
</div>
<div>Area: {area}m<sup>2</sup></div>
<div>Volume: {volume}m<sup>3</sup></div>
