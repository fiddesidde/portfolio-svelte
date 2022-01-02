<script>
  import { slide } from "svelte/transition";

  export let title;

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
    </div>
  {/if}
</div>

<style>
  .arrow {
    width: 12px;
  }
</style>
