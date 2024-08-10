<script>
  import UserProfile from './UserProfile.svelte';
  import Button from './Button.svelte';
  import PropsTest from './PropsTest.svelte';

  let keith = {
    name: 'Keith Noguchi',
    id: 'keithnoguchi',
    bio: 'C, Rust, and Svelte!',
  };
  let props = {label: "You can't click it.", disabled: true};
</script>

<UserProfile user={keith} />
<Button {...props} />

<PropsTest foo="test" bar={42} />
