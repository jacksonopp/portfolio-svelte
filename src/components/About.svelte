<script lang="ts">
  import Icon from "./Icon.svelte";
  const src = "/img/profileSM.bf9e50c5.png";
</script>

<style type="text/scss">
  div {
    color: white;
    display: grid;
    grid-template-columns: 2fr 1fr;
    grid-template-rows: 3fr 2fr;
    grid-template-areas:
      "description photo"
      "link .";
    row-gap: 1rem;
    column-gap: 1rem;
  }

  .description {
    grid-area: description;
  }

  .photo {
    grid-area: photo;
  }

  .link {
    grid-area: link;
    justify-self: center;
    display: flex;
    justify-content: space-evenly;
    width: 100%;
  }

  img {
    width: 300px;
    height: 300px;
    object-fit: cover;
    border-radius: 50%;
  }
</style>

<div>
  <section class="description">
    <h1>About Me</h1>
    <p>
      UX Engineer and Designer using a background in commercial entertainment to
      build engaging experiences on the web.
    </p>
    <p>
      At Pearson VUE, I'm proudly building the future of test taking in an
      increasingly online world with some of the brightest innovators in the
      EdTech world. I've designed UX for all scopes: from small things like an
      accessible drag-and-drop to big things like the interface of AI facial
      recognition software that's been seen in front of nearly 10M customers!
    </p>
  </section>
  <img class="photo" {src} alt="Portrait of Jackson" />
  <div class="link">
    <a href="http://www.github.com/jacksonopp" aria-label="Github">
      <Icon iconAbbr="github" size="8x" />
    </a>
    <a href="http://www.linkedin.com/in/jacksonopp" aria-label="Linkedin">
      <Icon iconAbbr="linkedin" size="8x" />
    </a>
  </div>
</div>
