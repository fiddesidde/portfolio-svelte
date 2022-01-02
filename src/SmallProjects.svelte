<script>
  import { smallProjects } from "./content/content.js";
  import { slide } from "svelte/transition";

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
    Small JS projects
  </h2>
  {#if showInfo}
    <div
      class="description full-project-div"
      transition:slide={{
        duration: 300,
      }}>
      {#each smallProjects as project}
        <div class="small-proj">
          <span class="small-title">{project.title}:</span>
          <span class="nav-item small-git"
            ><a href={project.gh} target="blank" rel="noopener">GitHub</a
            ></span>
          <span class="nav-item small-live"
            ><a href={project.live} target="blank" rel="noopener"
              >Live Preview</a
            ></span>
        </div>
      {/each}
    </div>
  {/if}
</div>

<style>
  .arrow {
    width: 12px;
  }

  .small-proj {
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
  }

  .small-git {
    margin-left: 10px;
  }

  .small-live {
    margin-right: 0;
  }

  .small-title {
    margin-right: auto;
  }

  @media (max-width: 380px) {
    .small-proj {
      flex-direction: column;
      align-items: flex-start;
    }
    .small-title {
      text-decoration: underline;
      margin-top: 10px;
    }
    .small-git {
      margin-left: 0;
      margin-right: 0;
    }
    .small-live {
      margin-bottom: 10px;
    }
  }
</style>
