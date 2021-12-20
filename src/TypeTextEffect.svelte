<script>
  let i = 0;
  export let text;
  const speed = 50;
  let output = "";
  const typeEffect = () => {
    if (i < text.length) {
      output += text.charAt(i);
      i++;
      setTimeout(typeEffect, speed);
    }
  };
  typeEffect();
</script>

{output}
