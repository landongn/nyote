<script>
	import Nav from '../components/Nav.svelte';

	export let searchBoxTextValue = "";
</script>

<style>
	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 2em;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>

<header>
	<section>nYote</section>
	<section class="search"><input value="{searchBoxTextValue}" type="text" placeholder="Search..." /></section>
</header>

<main>
	<slot></slot>
</main>