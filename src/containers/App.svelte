<script>
  import Header from "../components/Header.svelte";
  import Main from "../components/Main.svelte";
  import TimeLine from "../components/TimeLine.svelte";
  import Sidebar from "../components/Sidebar.svelte";
</script>

<div>
  <Header />
  <main>
    <TimeLine />
    <Sidebar />
  </main>
</div>

<style>
  :global(body) {
    background-color: #676778;
    color: #fff;
  }
</style>
