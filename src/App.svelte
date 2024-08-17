<script>
  import HelloButton from './HelloButton.svelte';

  function handleHello(event) {
    alert(event.detail);
  }
</script>

<HelloButton on:hello={handleHello} />
