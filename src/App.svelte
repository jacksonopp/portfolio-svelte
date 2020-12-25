<script lang="ts">
	import About from "./components/About.svelte";
	import Contact from "./components/Contact.svelte";
	import Name from "./components/Name.svelte";
	import Navbar from "./components/Navbar.svelte";
	import Portfolio from "./components/Portfolio.svelte";
	import Spacer from "./components/Spacer.svelte";

	let isNavbarDisplayed = true;
	let height = 20;
</script>

<style type="text/scss">
	$link-color: #fff8f0;

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

		&:hover {
			color: darken($color: $link-color, $amount: 20);
		}
	}

	:global(article) {
		min-height: 100vh;
	}

	main {
		background-color: rebeccapurple;
		min-height: 100vh;
		&.open {
			display: grid;
			grid-template-columns: 1fr 5fr;
		}
		&.closed {
			grid-template-columns: 1fr 10fr;

			.section {
				margin-left: 5rem;
			}
		}
	}

	section {
		padding: 1rem;
	}

	.section {
		min-height: 100vh;
	}
</style>

<svelte:head>
	<title>Jackson Oppenheim</title>
</svelte:head>

<main class={isNavbarDisplayed ? 'open' : 'closed'}>
	<!-- on:display-change={({ detail }) => handleDisplayChange(detail)} -->
	<div class="navbar">
		<Navbar bind:shouldShowNavbar={isNavbarDisplayed} />
	</div>
	<div class="content">
		<Name />
		<Spacer {height} />
		<div class="section" id="about-me">
			<About />
		</div>
		<Spacer {height} />
		<div class="section" id="portfolio ml">
			<Portfolio />
		</div>
		<Spacer {height} />
		<div class="section" id="contact">
			<Contact />
		</div>
	</div>
</main>
