<script>
	import FmlControls from './fml-controls/fml-controls.svelte'
</script>

<main>
	<FmlControls />
</main>

<style>
	:global(body) {
		background-color: #eee;
	}

	:global(.material-icons) {
		user-select: none;
	}
	
	:global(input) {
		-webkit-appearance: none;
		appearance: none;
		border: none;
	}

	:global(button:not(:disabled):active) {
		background-color: unset;
	}

	main {
		min-height: 100%;
		padding: 3rem 1rem;
	}
</style>