<script lang="ts">
  export let title: string;
  export let photoUrl: string;
  export let githubUrl: string;
  export let appUrl: string;
</script>

<style type="text/scss">
  .portfolio-item {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    margin-bottom: 1rem;
    box-shadow: 5px 5px 10px 1px rgba(0, 0, 0, 0.3);
    background-color: #000;

    img {
      transition: all 0.3s;
      min-width: 100%;
      max-height: 300px;
      object-fit: cover;
      opacity: 0.4;
    }

    .portfolio-title {
      position: absolute;
      text-align: center;
      padding: 0;
      width: 100%;
      background-color: rgba(42, 157, 143, 0.7);
      box-shadow: 0 2px 5px 1px rgba(0, 0, 0, 0.3);
      color: #fff;
      transition: all 0.3s;

      &:hover {
        background-color: lighten($color: rgba(42, 157, 143, 0.7), $amount: 7);
      }
    }

    .links {
      position: absolute;
      align-self: flex-end;
      display: flex;
      width: 100%;
      justify-content: space-evenly;
      bottom: 1rem;
    }

    .link-btn {
      background-color: rgba(42, 157, 143, 0.7);
      color: #fff;
      padding: 1rem;
      border-radius: 4px;
      box-shadow: 2px 2px 5px 1px rgba(0, 0, 0, 0.3);
      transition: all 0.3s;

      &:hover {
        background-color: lighten($color: rgba(42, 157, 143, 0.7), $amount: 7);
      }
    }

    &:hover {
      img {
        opacity: 1;
      }
    }
  }
</style>

<div class="portfolio-item">
  <img loading="lazy" src={photoUrl} alt={title} />
  <div class="portfolio-title">
    <h3>{title}</h3>
  </div>
  <div class="links">
    <a class="link-btn" href={githubUrl}>Github</a>
    <a class="link-btn" href={appUrl}>App</a>
  </div>
</div>
