<script>
  let isDarkMode = false;

  const toggleMode = () => {
    isDarkMode = !isDarkMode;

    const body = document.querySelector("body");
    if (isDarkMode) {
      body.classList.add("dark");
      body.classList.remove("light");
    } else {
      body.classList.remove("dark");
      body.classList.add("light");
    }
  };
</script>

<nav class="navbar">
  {#if isDarkMode}
    <svg
      on:click={() => toggleMode()}
      width="16"
      height="16"
      fill="#ffff00"
      class="mode-icon"
      viewBox="0 0 16 16"
      ><title id="svg-title">Let it shine!</title>
      <path
        d="M8 12a4 4 0 1 0 0-8 4 4 0 0 0 0 8zM8 0a.5.5 0 0 1 .5.5v2a.5.5 0 0 1-1 0v-2A.5.5 0 0 1 8 0zm0 13a.5.5 0 0 1 .5.5v2a.5.5 0 0 1-1 0v-2A.5.5 0 0 1 8 13zm8-5a.5.5 0 0 1-.5.5h-2a.5.5 0 0 1 0-1h2a.5.5 0 0 1 .5.5zM3 8a.5.5 0 0 1-.5.5h-2a.5.5 0 0 1 0-1h2A.5.5 0 0 1 3 8zm10.657-5.657a.5.5 0 0 1 0 .707l-1.414 1.415a.5.5 0 1 1-.707-.708l1.414-1.414a.5.5 0 0 1 .707 0zm-9.193 9.193a.5.5 0 0 1 0 .707L3.05 13.657a.5.5 0 0 1-.707-.707l1.414-1.414a.5.5 0 0 1 .707 0zm9.193 2.121a.5.5 0 0 1-.707 0l-1.414-1.414a.5.5 0 0 1 .707-.707l1.414 1.414a.5.5 0 0 1 0 .707zM4.464 4.465a.5.5 0 0 1-.707 0L2.343 3.05a.5.5 0 1 1 .707-.707l1.414 1.414a.5.5 0 0 1 0 .708z" />
    </svg>
  {:else}
    <svg
      on:click={() => toggleMode()}
      width="16"
      height="16"
      fill="#3A7ACE"
      class="mode-icon"
      viewBox="0 0 16 16"
      ><title id="svg-title">Hit the lights!</title>
      <path
        d="M6 .278a.768.768 0 0 1 .08.858 7.208 7.208 0 0 0-.878 3.46c0 4.021 3.278 7.277 7.318 7.277.527 0 1.04-.055 1.533-.16a.787.787 0 0 1 .81.316.733.733 0 0 1-.031.893A8.349 8.349 0 0 1 8.344 16C3.734 16 0 12.286 0 7.71 0 4.266 2.114 1.312 5.124.06A.752.752 0 0 1 6 .278z" />
    </svg>
  {/if}
  <span class="nav-item nav-span"
    ><a href="https://github.com/fiddesidde" target="_blank" rel="noopener"
      >GitHub</a
    ></span>
  <span class="nav-item nav-span"
    ><a
      href="https://www.linkedin.com/in/fredrik-mellberg/"
      target="_blank"
      rel="noopener">LinkedIn</a
    ></span>
</nav>

<style>
  .navbar {
    display: flex;
    flex-direction: row;
  }

  .nav-span {
    margin-top: 4px;
  }

  .mode-icon {
    margin-top: 7px;
    margin-left: 10px;
    margin-right: auto;
    cursor: pointer;
  }
</style>
