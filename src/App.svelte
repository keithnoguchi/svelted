<script>
  import Count from './Count.svelte';
</script>

<Count>
  <span slot="count" let:value={v}>{v}</span>
</Count>
