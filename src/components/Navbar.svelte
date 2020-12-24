<script lang="ts">
  import { createEventDispatcher } from "svelte";

  import Hamburger from "./Hamburger.svelte";

  export let shouldShowNavbar: boolean;

  const emit = createEventDispatcher();

  function showOrHideNavbar(): void {
    shouldShowNavbar = !shouldShowNavbar;
  }
</script>

<style type="text/scss">
  ul {
    li {
      margin-bottom: 2rem;
      list-style: none;
      font-size: 1.2rem;
    }
  }

  button {
    border: none;
    background-color: transparent;
    padding: 0;
    margin: 0;

    &.times {
      font-size: 2.5rem;
      margin: 0 1rem;
      &:active {
        color: transparentize($color: #000000, $amount: 0.7);
      }
    }

    &:active {
      background-color: transparent;
    }
  }

  .show-nav {
    display: flex;
    align-items: start;
    height: 100vh;
    background-color: white;
    box-shadow: inset -7px 0 9px -7px rgba(0, 0, 0, 0.3);
    position: fixed;
    left: 0;

    ul {
      margin-top: 3rem;
    }
  }
</style>

{#if shouldShowNavbar}
  <!-- content here -->
  <nav class="show-nav">
    <ul>
      <li><a href="#about-me" on:click={showOrHideNavbar}>About Me</a></li>
      <li><a href="#portfolio" on:click={showOrHideNavbar}>Portfolio</a></li>
      <li><a href="#contact" on:click={showOrHideNavbar}>Contact</a></li>
    </ul>
    <button class="times" on:click={showOrHideNavbar}>&times;</button>
  </nav>
{:else}
  <!-- else content here -->
  <nav class="hide-nav">
    <Hamburger on:hamburger-clicked={showOrHideNavbar} />
  </nav>
{/if}
