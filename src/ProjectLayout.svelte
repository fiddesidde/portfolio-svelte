<script>
  import { slide } from "svelte/transition";

  export let title;
  export let gh;
  export let live;

  let showInfo = false;

  function toggleShow() {
    showInfo = !showInfo;
  }
</script>

<div class="card">
  {#if showInfo}
    <h2 class="proj-head" on:click={() => toggleShow()}>
      {title}
    </h2>
    <div
      class="description full-project-div"
      style="display: block;"
      transition:slide={{
        duration: 300,
      }}>
      <slot />
      <div class="links">
        Take a closer look:
        <div>
          <span class="nav-item"
            ><a href={gh} target="_blank" rel="noopener">GitHub</a></span>
          <span class="nav-item"
            ><a href={live} target="_blank" rel="noopener">Live Preview</a
            ></span>
        </div>
      </div>
    </div>
  {:else}
    <h2
      class="proj-head"
      on:click={() => toggleShow()}
      in:slide={{ delay: 301, duration: 0 }}>
      {title}...<span class="show-more">show more</span>
    </h2>
  {/if}
</div>

<style>
  .show-more {
    font-size: 14px;
  }
</style>
