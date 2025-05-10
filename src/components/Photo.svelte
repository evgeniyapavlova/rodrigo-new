<script>
	import { base } from '$app/paths';

	export let photo,
		no2x = true;
</script>

{#if no2x}
	<picture class={photo}>
		<source srcset="{base}/images/{photo}.avif" type="image/avif" />
		<source srcset="{base}/images/{photo}.webp" type="image/webp" />
		<img src="{base}/images/{photo}.jpg" alt="Presenter" />
	</picture>
{:else}
	<picture class={photo}>
		<source
			srcset="{base}/images/{photo}.avif 1x, {base}/images/{photo}@2x.avif 2x"
			type="image/avif"
		/>
		<source
			srcset="{base}/images/{photo}.webp 1x, {base}/images/{photo}@2x.webp 2x"
			type="image/webp"
		/>
		<img
			src="{base}/images/{photo}.jpg"
			srcset="{base}/images/{photo}.jpg 1x, {base}/images/{photo}@2x.jpg 2x"
			alt="Presenter"
		/>
	</picture>
{/if}
