<script>
  import BigCard from "./BigCard.svelte";
  import SmallProjects from "./SmallProjects.svelte";
  import TypeTextEffect from "./TypeTextEffect.svelte";
  import Navbar from "./Navbar.svelte";
  import { projects } from "./content";
  import Md from "./content/monly.md";
</script>

<main>
  <div id="container">
    <Navbar />
    <div id="main">
      <header class="header">
        <h1><TypeTextEffect text={"Portfolio, Fredrik Mellberg"} /></h1>
      </header>
      <section class="section">
        Hi! Welcome to my portfolio site. Check out my projects below.<br />I'm
        currently employed as a HVAC-engineer looking to make a career change
        into web development, primarily in back-end development.<br />To hire
        me, contact me here:
        <span class="nav-item"
          ><a href="mailto:fredrik@fremworks.com">fredrik@fremworks.com</a
          ></span>
      </section>
      <section id="card-container">
        {#each projects as project, i}
          <BigCard id={i} {project} />
        {/each}
        <Md />
        <SmallProjects />
      </section>
    </div>
  </div>
</main>

<style>
  #container {
    display: flex;
    flex-direction: column;
  }

  .header {
    justify-self: center;
    margin-top: 50px;
  }

  #main {
    display: flex;
    justify-content: center;
    align-items: flex-start;
    flex-direction: column;
    margin: 40px 20% 30px 20%;
  }

  .section {
    line-height: 2rem;
  }

  #card-container {
    flex-direction: column;
    margin-top: 50px;
    justify-content: center;
    width: 100%;
  }

  @media (max-width: 540px) {
    #main {
      margin-left: 7%;
      margin-right: 7%;
    }
  }
</style>
