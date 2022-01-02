<script>
  import { slide, fade } from "svelte/transition";

  export let title;
  export let gh;
  export let live;

  const rightArrowUrl = "/arrow-right-solid.svg";
  const downArrowUrl = "/arrow-down-solid.svg";

  let arrowUrl = rightArrowUrl;

  let showInfo = false;

  function toggleShow() {
    showInfo = !showInfo;
    arrowUrl = arrowUrl === downArrowUrl ? rightArrowUrl : downArrowUrl;
  }
</script>

<div class="card">
  <h2 class="proj-head" on:click={() => toggleShow()}>
    <img src={arrowUrl} alt="" class="arrow" />
    {title}
  </h2>
  {#if showInfo}
    <div
      class="description full-project-div"
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
  {/if}
</div>

<style>
  .arrow {
    width: 12px;
  }
</style>
