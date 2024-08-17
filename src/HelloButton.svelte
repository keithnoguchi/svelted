<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  function handleClick() {
    dispatch('hello', 'こんにちは!');
  }
</script>

<button on:click|once={handleClick}>Click it!</button>
