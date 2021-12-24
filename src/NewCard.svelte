<script>
  let title;
  import Stuff from "./stuff.svelte";
  let showInfo = false;

  function toggleShow() {
    showInfo = !showInfo;
  }
</script>

<div on:click={() => toggleShow()} class="card">
  <h2 class="proj-head">{title}</h2>
  {#if showInfo}
    <Stuff bind:title />
  {:else}
    <div class="description">More...</div>
  {/if}
</div>
