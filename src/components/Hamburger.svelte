<script lang="ts">
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  function onHamburgerClick(): void {
    dispatch("hamburger-clicked");
  }
</script>

<style type="text/scss">
  button {
    border: none;
    background-color: transparent;
    fill: #fff8f0;

    &:hover {
      cursor: pointer;
    }
    &:active {
      background-color: transparent;

      > svg {
        fill: transparentize($color: #fff8f0, $amount: 0.7);
      }
    }
  }
</style>

<button on:click={onHamburgerClick}>
  <svg viewBox="0 0 100 80" width="40" height="40">
    <rect width="100" height="20" />
    <rect y="30" width="100" height="20" />
    <rect y="60" width="100" height="20" />
  </svg>
</button>
