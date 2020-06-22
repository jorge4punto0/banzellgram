<script>
  import Profile from './Profile.svelte';
  import Stories from './Stories.svelte';
  import Footer from './Footer.svelte';

  export let nickname;
  export let name;

</script>

<div class="Sidebar">
  <div class="Sidebar__container">
    <Profile {nickname} {name} />
    <Stories />
    <Footer />
  </div>
</div>

<style>
  .Sidebar {
    position: fixed;
    position: relative;
    padding: 4.5em 0 0 0;
  }
  .Sidebar__container {
    position: fixed;
  }
</style>
