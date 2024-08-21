<script>
  import { beforeUpdate, afterUpdate } from 'svelte';

  let prevHeight;

  beforeUpdate(() => {
    const element = document.getElementById('timeline');

    // Make sure the element exists.
    if (element) {
      prevHeight = element.scrollHeight;
    } else {
      console.log('no timeline element in the doc yet.');
    }
  });

  afterUpdate(() => {
    if (prevHeight) {
      const element = document.getElementById('timeline');
      const diff = element.scrollHeight - prevHeight;
      element.scrollTop += diff;
    }
  });

  let contents = Array.from({length: 100}, (_, i) => `Post #${i}`);

  function handleClick() {
    contents = [
      ...Array.from({length: 100}, (_, i) => `Post #${i - 100}`),
      ...contents,
    ];
  }
</script>

<div id="timeline">
  {#each contents as post}
    <div>{post}</div>
  {/each}
</div>

<button on:click={handleClick}>
  Updat timeline
</button>

<style>
  #timeline {
    width: 300px;
    height: 300px;
    border: 1px solid gray;
    overflow: auto;
  }
</style>
