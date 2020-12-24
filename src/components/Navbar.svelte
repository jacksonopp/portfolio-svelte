<script lang="ts">
  import { createEventDispatcher, onMount } from "svelte";

  import Hamburger from "./Hamburger.svelte";

  export let shouldShowNavbar: boolean;

  onMount(() => {
    shouldShowNavbar = isScreenLarge();
  });

  const emit = createEventDispatcher();

  function isScreenLarge(): boolean {
    return window.innerWidth > 1200;
  }

  function showOrHideNavbar(shouldUseSize: boolean): void {
    if (shouldUseSize) {
      if (!isScreenLarge()) {
        shouldShowNavbar = !shouldShowNavbar;
        return;
      }
      return;
    }
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

  .hide-nav {
    position: fixed;
    top: 1.5rem;
    left: 1.5rem;
  }
</style>

{#if shouldShowNavbar}
  <!-- content here -->
  <nav class="show-nav">
    <ul>
      <li>
        <a href="#about-me" on:click={() => showOrHideNavbar(true)}>About Me</a>
      </li>
      <li>
        <a
          href="#portfolio"
          on:click={() => showOrHideNavbar(true)}>Portfolio</a>
      </li>
      <li>
        <a href="#contact" on:click={() => showOrHideNavbar(true)}>Contact</a>
      </li>
    </ul>
    <button
      class="times"
      on:click={() => showOrHideNavbar(false)}>&times;</button>
  </nav>
{:else}
  <!-- else content here -->
  <nav class="hide-nav">
    <Hamburger on:hamburger-clicked={() => showOrHideNavbar(false)} />
  </nav>
{/if}
