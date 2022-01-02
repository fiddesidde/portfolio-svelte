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
    {#if showInfo}
      <svg
        aria-hidden="true"
        focusable="false"
        class="arrow"
        viewBox="0 0 448 512"
        ><path
          fill="var(--font)"
          d="M413.1 222.5l22.2 22.2c9.4 9.4 9.4 24.6 0 33.9L241 473c-9.4 9.4-24.6 9.4-33.9 0L12.7 278.6c-9.4-9.4-9.4-24.6 0-33.9l22.2-22.2c9.5-9.5 25-9.3 34.3.4L184 343.4V56c0-13.3 10.7-24 24-24h32c13.3 0 24 10.7 24 24v287.4l114.8-120.5c9.3-9.8 24.8-10 34.3-.4z" /></svg>
    {:else}
      <svg
        aria-hidden="true"
        focusable="false"
        class="arrow"
        viewBox="0 0 448 512"
        ><path
          fill="var(--font)"
          d="M190.5 66.9l22.2-22.2c9.4-9.4 24.6-9.4 33.9 0L441 239c9.4 9.4 9.4 24.6 0 33.9L246.6 467.3c-9.4 9.4-24.6 9.4-33.9 0l-22.2-22.2c-9.5-9.5-9.3-25 .4-34.3L311.4 296H24c-13.3 0-24-10.7-24-24v-32c0-13.3 10.7-24 24-24h287.4L190.9 101.2c-9.8-9.3-10-24.8-.4-34.3z" /></svg>
    {/if}
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
