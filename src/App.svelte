<script>
  function handleSubmit(e) {
    e.preventDefault();
    const formData = new FormData(e.target);
    alert(`"${formData.get('q')}" is the search keyword.`);
  }
</script>

<form on:submit={handleSubmit}>
  <input type="search" name="q">
  <button type="submit">Search</button>
</form>
