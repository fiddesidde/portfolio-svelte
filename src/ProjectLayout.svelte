<script>
  export let gh;
  export let live;
  export let title;
</script>

<slot />
<div class="links">
  Take a closer look:
  <div>
    <span class="nav-item"
      ><a href={gh} target="_blank" rel="noopener">GitHub</a></span>
    <span class="nav-item"
      ><a href={live} target="_blank" rel="noopener">Live Preview</a></span>
  </div>
</div>
