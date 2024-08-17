<script>
  import CustomButton from './CustomButton.svelte';

  function handler(e) {
    console.log(e.constructor.name);
    alert("You did it!");
  }
</script>

<CustomButton on:click|once={handler}>
  Click here!
</CustomButton>
