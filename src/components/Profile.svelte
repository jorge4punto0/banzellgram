<script>
  export let nickname;
  export let name;

</script>

<div class="Profile">
  <div class="Profile__content">
    <div class="Profile__userImg">
      <img src="https://avatars2.githubusercontent.com/u/34985840?s=460&u=6662d23205daab5d63c766ce60572d162929d93d&v=4" alt="">
    </div>
    <div class="Profile__info">
      <h2>{nickname}</h2>
      <span>{name}</span>
    </div>
  </div>
</div>

<style>
  .Profile__content {
    display: flex;
    align-items: center;
  }
  .Profile__userImg img {
    width: 42px;
    height: 42px;
    border-radius: 50%;
  }
  .Profile__info {
    margin: 0 0 0 0.5em;
  }
  .Profile__info h2 {
    font-size: 14px;
    color: black;
    margin: 0;
    padding: 0;
  }
  .Profile__info span {
    font-size: 12px;
    font-weight: normal;
  }
</style>