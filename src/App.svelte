<script>
  function handleClick() {
    alert('You clicked the div element.');
  }

  function handleButtonClick() {
    alert('You clicked the button element.');
  }
</script>

<div on:click|capture|stopPropagation={handleClick}>
  <button on:click={handleButtonClick}>Click it!</button>
</div>
