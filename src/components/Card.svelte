<script>
  import Comments from './Comments.svelte';
  import Modal from './Modal.svelte';
  import Share from './Share.svelte';

  import { blur } from 'svelte/transition';

  export let username;
  export let location;
  export let photo;
  export let postComment;
  export let comment;
  export let avatar;

  let isModal = false;
  let like = false;
  let bookmark = false;

  function handleClickModal() {
    isModal = !isModal;
  }

  function handleClickLike() {
    like = !like;
  }
</script>

<div class="Card">
  {#if isModal}
    <div transition:blur >
      <Modal>
        <Share on:click={handleClickModal} />
      </Modal>
    </div>
  {/if}
  <div class="Card__container">
    <div class="Card__header">
      <div class="Card__user">
        <img src={avatar} alt={username}>
        <h2>{username} <span>{location}</span></h2>
      </div>
      <div class="Card__settings">
        <i class="fas fa-ellipsis-h" />
      </div>
    </div>
    <div class="Card__photo">
      <figure on:dblclick={handleClickLike}>
        <img src={photo} alt={username}>
      </figure>
    </div>
    <div class="Card__icons">
      <div class="Card__icons-first">
        <i
          class="fas fa-heart"
          class:active-like={like}
          on:click={handleClickLike}
        />
        <i class="fas fa-paper-plane" on:click={handleClickModal} />
      </div>
      <div class="Card__icons-second">
        <i
          class="fas fa-bookmark"
          class:active-bookmark={bookmark}
          on:click={() => (bookmark = !bookmark)}
        />
      </div>
    </div>
    <div class="Card__description">
      <h3>{username}</h3>
      <span>{postComment}</span>
    </div>
    <Comments />
  </div>
</div>

<style>
  .Card {
    border: 1px solid rgba(219, 219, 219, 1);
    border-radius: 4px;
    background-color: white;
    margin: 0 0 2em 0;
  }
  .Card__header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1em;
  }
  .Card__user {
    display: flex;
    align-items: center;
    justify-content: flex-end;
  }
  .Card__user img {
    width: 32px;
    height: 32px;
    border-radius: 50%;
  }
  .Card__user h2 {
    margin: 0;
    padding: 0;
    font-size: 14px;
    font-weight: 600;
    margin: 0 0 0 1em;
    color: black;
  }
  .Card__user h2 span {
    display: block;
    font-size: 12px;
    font-weight: normal;
    color: rgba(38, 38, 38, 0.7);
  }
  .Card__photo {
    padding: 0;
    margin: 0;
  }
  .Card__photo img {
    width: 100%;
    height: auto;
  }
  .Card__photo figure {
    margin: 0;
    padding: 0;
    cursor: pointer;
  }
  .Card__settings i {
    cursor: pointer;
  }
  .Card__icons {
    padding: 1em;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  .Card__icons i {
    margin: 0 1em 0 0;
    cursor: pointer;
    font-size: 20px;
  }
  .Card__icons i:last-child {
    margin: 0;
  }
  .Card__description {
    padding: 0 1em 1em 1em;
  }
  .Card__description h3 {
    font-size: 14px;
    font-weight: bold;
    color: black;
  }
  .Card__description span {
    font-size: 14px;
  }
  .active-like {
    color: #bc1888;
    animation: bounce linear 0.8s;
    animation-iteration-count: 1;
    transform-origin: 20% 20%;
  }
  .active-bookmark {
    color: #f09433;
  }

  @keyframes bounce {
    0% {
      transform: translate(0px, 0px);
    }
    15% {
      transform: translate(0px, -25px);
    }
    30% {
      transform: translate(0px, 0px);
    }
    45% {
      transform: translate(0px, -15px);
    }
    60% {
      transform: translate(0px, 0px);
    }
    75% {
      transform: translate(0px, -5px);
    }
    100% {
      transform: translate(0px, 0px);
    }
  }
</style>
