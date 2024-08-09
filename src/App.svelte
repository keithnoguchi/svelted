<script>
  let timeout = 3000;
  let promise = new Promise((resolve, reject) => {
    setTimeout(() => resolve(`${timeout} seconds passed.`), timeout);
  });
</script>

{#await promise then message}
  <p>{message}</p>
{/await}
