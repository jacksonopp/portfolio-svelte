<script lang="ts">
	import Name from "./components/Name.svelte";
	import Navbar from "./components/Navbar.svelte";

	let isNavbarDisplayed = true;
	let randomValue = 0;
</script>

<style type="text/scss">
	$link-color: #2a9d8f;

	:global(body) {
		margin: 0;
		padding: 0;
	}

	:global(a) {
		text-decoration: none;
		color: $link-color;

		&:visited {
			color: $link-color;
		}
	}

	:global(article) {
		min-height: 100vh;
	}

	main {
		display: grid;
		background-color: rebeccapurple;
		min-height: 100vh;
		&.open {
			grid-template-columns: 1fr 5fr;
		}
		&.closed {
			grid-template-columns: 1fr 10fr;
		}
	}

	section {
		padding: 1rem;
	}
</style>

<main class={isNavbarDisplayed ? 'open' : 'closed'}>
	<!-- on:display-change={({ detail }) => handleDisplayChange(detail)} -->
	<div class="navbar">
		<Navbar bind:shouldShowNavbar={isNavbarDisplayed} />
	</div>
	<div class="content">
		<Name />
	</div>
</main>
