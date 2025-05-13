<script>
	import { onMount } from 'svelte';
	import { getURLParameters } from '$lib/utils/getAffParams';
	import { searchString } from '$lib/stores/affs';
	import '$lib/styles/styles.scss';
	import '$lib/styles/buttons.scss';
	import '$lib/styles/fonts.scss';

	onMount(() => {
		$searchString = getURLParameters();
	});
</script>

<div class="app">
	<slot />
</div>

<style>
	.app {
		display: flex;
		flex-direction: column;
		min-height: 100vh;
		overflow: hidden;
	}
</style>
