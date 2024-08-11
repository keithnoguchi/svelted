<script>
  import Box from './Box.svelte';
  import Button from './Button.svelte';
  let label = 'Send it!';
  let disabled = true;
  let condition = false;
</script>

<Box>
  <h3>About Svelte</h3>
  <p>
    <a href="https://svelte.dev">Svelte</a> is a UI framework
    to create cybernetically enhanced web apps.
  </p>
  <Button {label} {disabled} />

  {#if condition}
    <div>...</div>
  {/if}
</Box>
<Box />
