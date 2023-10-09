<script>
  import Modal from 'svelte-easy-modal';
  let showModal = false;
  import Popup from './popup.svelte';
  $: console.log(showModal);
</script>

<main>
  <h1>svelte-easy-modal</h1>
  <Modal
    showHeader={true}
    showClose={true}
    outsideClose={true}
    insideClose={true}
    bind:showModal
  >
    <h1 class="header" slot="header">Header</h1>
    <Popup />
  </Modal>
  <button on:click={() => (showModal = !showModal)}> OPEN MODAL </button>
</main>

<style>
  main {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .header {
    color: blue;
  }
  button {
    width: 150px;
    height: 60px;
    font-size: 1.1rem;
    font-weight: bold;
  }
</style>
