<script>
  const gh = "https://github.com/fiddesidde/odin-members-only";
  const live = "https://fremworks.com/monly/";
  export const title = "Members Only";
</script>

<div class="description full-project-div" style="display: block;">
  This is a SSR app I made during the course of
  <span class="nav-item"
    ><a
      href="https://www.theodinproject.com/home"
      target="_blank"
      rel="noopener">"The Odin Project"</a
    >,</span
  >primarily to learn authentication and authorization.The app is a messaging
  board where, depending on the users "tier", different information is available
  to view and actions to take.<br />The technology used is:
  <ul>
    <li>NodeJS</li>
    <li>Express</li>
    <li>MongoDB</li>
    <li>EJS</li>
    <li>Bootstrap</li>
  </ul>
  The app is hosted on a RaspberryPi, same as this site, running Ubuntu Server with
  an NGINX reverse proxy.<br /><br />Go ahead and try the app. Use the
  passphrase "banana" to upgrade the user tier to "Member" status.
  <div class="links">
    Take a closer look:
    <div>
      <span class="nav-item"
        ><a href={gh} target="_blank" rel="noopener">GitHub</a></span>
      <span class="nav-item"
        ><a href={live} target="_blank" rel="noopener">Live Preview</a></span>
    </div>
  </div>
</div>

<style>
  .links {
    margin-top: 1.2rem;
  }
</style>
