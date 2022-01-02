<script>
  import { smallProjects } from "./content/content.js";
</script>

{#each smallProjects as project}
  <div class="small-proj">
    <span class="small-title">{project.title}:</span>
    <span class="nav-item small-git"
      ><a href={project.gh} target="blank" rel="noopener">GitHub</a></span>
    <span class="nav-item small-live"
      ><a href={project.live} target="blank" rel="noopener">Live Preview</a
      ></span>
  </div>
{/each}

<style>
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
