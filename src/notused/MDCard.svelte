<!-- <script context="module">
  let posts = import.meta.globEager("./content/*.md");
</script> -->
<script>
  // posts;
  let id = 0;
  export let project;
  console.log("project:", project);
  let { title, info = "", gh, live } = project;
  let showInfo = false;

  function toggleShow() {
    showInfo = !showInfo;
  }
</script>

{project}

<div on:click={() => toggleShow()} class="card" {id}>
  <h2 class="proj-head">{title}</h2>
  {#if showInfo}
    <div class="description full-project-div" style="display: block;">
      {@html info}
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
    <div class="description">More...</div>
  {/if}
</div>

<style>
  .links {
    margin-top: 1.2rem;
  }
</style>
