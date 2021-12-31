<script>
  export let url;
  export let text;
</script>

<a href={url} target="_blank" rel="noopener">{text}</a>

<style>
  a {
    color: var(--font);
    text-decoration: none;
  }

  a:hover {
    text-decoration: underline;
  }
</style>
