<script>
  import { smallProjects } from "./content/content.js";
  import { slide } from "svelte/transition";

  let showInfo = false;

  function toggleShow() {
    showInfo = !showInfo;
  }
</script>

<div class="card">
  {#if showInfo}
    <h2 class="proj-head" on:click={() => toggleShow()}>
      <img src="/arrow-down-solid.svg" alt="" class="arrow" />
      Small JS projects
    </h2>
    <div
      class="description full-project-div"
      style="display: block;"
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
  {:else}
    <h2
      class="proj-head"
      on:click={() => toggleShow()}
      in:slide={{ delay: 300, duration: 0 }}>
      <img src="/arrow-right-solid.svg" alt="" class="arrow" />
      Small JS projects
    </h2>
  {/if}
</div>

<style>
  .arrow {
    display: inline-block;
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
