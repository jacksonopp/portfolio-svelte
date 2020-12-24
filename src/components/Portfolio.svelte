<script lang="ts">
  import PortfolioItem from "./PortfolioItem.svelte";

  class PortfolioItemModel {
    constructor(
      public photoUrl: string,
      public title: string,
      public githubUrl: string,
      public appUrl: string
    ) {}
  }

  const data: PortfolioItemModel[] = [
    new PortfolioItemModel(
      "http://www.placekitten.com/1000/500",
      "a title",
      "a github url",
      "an app url"
    ),
    new PortfolioItemModel(
      "http://www.placekitten.com/1000/500",
      "a title",
      "a github url",
      "an app url"
    ),
  ];
</script>

<style type="text/scss">
  .portfolio {
    padding: 1rem;
  }
</style>

<div class="portfolio">
  {#each data as item}
    <PortfolioItem
      photoUrl={item.photoUrl}
      title={item.title}
      githubUrl={item.githubUrl}
      appUrl={item.appUrl} />
  {/each}
</div>
