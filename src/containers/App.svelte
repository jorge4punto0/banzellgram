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
  @import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;1,300&family=Pacifico&display=swap');

    :global(:root) {
/* COLORS */
	--first-color: #f2eee2;

/* FONTS */
  --first-font: 'Lato', sans-serif;
  --second-font: 'Pacifico', cursive;
}
  :global(body) {
    background-color: var(--first-color);
    color: rgba(38,38,38, 0,7);
    font-family: var(--first-font);
    margin: 0;
    padding: 0;
  }
  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
</style>
