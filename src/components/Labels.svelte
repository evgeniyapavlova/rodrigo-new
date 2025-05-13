<script>
	import Photo from './Photo.svelte';
    import "$lib/styles/labels.scss"
</script>

{#each [1, 2, 3] as i}
	<div class="label label-{i}">
		<Photo photo="label{i}" isPng />
	</div>
{/each}
