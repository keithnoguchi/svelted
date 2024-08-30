<script>
  let n = 1;

  $: if (n > 10) {
    alert('Too big number.  Set it less than or equal to 10.');
    n = 10;
  }
</script>

<div>
  Number: {n}
</div>
<div>
  <button on:click={() => (n -= 1)} disabled={n <= 1}>
    -
  </button>
  <button on:click={() => (n += 1)}>
    +
  </button>
</div>
