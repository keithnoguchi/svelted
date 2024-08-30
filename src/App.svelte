<script>
  let counter = 0;

  function countUp() {
    counter += 1;
  }
</script>

<button on:click={countUp}>
  {counter} clicked!
</button>
