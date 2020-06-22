<script>
  import { onMount } from 'svelte';

  import Header from "../components/Header.svelte";
  import Main from "../components/Main.svelte";
  import TimeLine from "../components/TimeLine.svelte";
  import Sidebar from "../components/Sidebar.svelte";

  let data = {};
  const API = 'https://us-central1-pugstagram-co.cloudfunctions.net/data';

  onMount(async () => {
    const response = await fetch(API);
    data = await response.json();
  });

</script>

<div>
  <Header />
  <Main>
    <TimeLine posts={data.posts} />
    <Sidebar {...data.user} />
  </Main>
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Lato:ital,wght@0,400;1,300&family=Pacifico&display=swap');

    :global(:root) {
/* COLORS */
	--first-color: #f2eee2;
	--second-color: #ffffff;

/* FONTS */
  --first-font: 'Lato', sans-serif;
  --second-font: 'Pacifico', cursive;

  /* SPACES */
}
  :global(body) {
    background-color: var(--first-color);
    color: rgba(38,38,38, 0,7);
    font-family: var(--first-font);
    padding: 0;
    margin: 0;
  }
  :global(h1, h2, h3) {
    margin: 0;
    padding: 0;
  }
</style>
