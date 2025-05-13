<script>
	import { base } from '$app/paths';

	export let photo,
		no2x = true,
		isPng = false,
		hasMobile = false;
</script>

{#if hasMobile}
	<picture class={photo}>
		<source media="(max-width: 1079px)" srcset="{base}/images/{photo}-mob.avif" type="image/avif" />
		<source media="(max-width: 1079px)" srcset="{base}/images/{photo}-mob.webp" type="image/webp" />

		<source
			media="(max-width: 1079px)"
			srcset="{base}/images/{photo}-mob.{isPng ? 'png' : 'jpg'}"
		/>

		<source srcset="{base}/images/{photo}.avif" type="image/avif" />
		<source srcset="{base}/images/{photo}.webp" type="image/webp" />
		<img src="{base}/images/{photo}.{isPng ? 'png' : 'jpg'}" alt="Presenter" />
	</picture>
{:else if no2x}
	<picture class={photo}>
		<source srcset="{base}/images/{photo}.avif" type="image/avif" />
		<source srcset="{base}/images/{photo}.webp" type="image/webp" />
		<img src="{base}/images/{photo}.{isPng ? 'png' : 'jpg'}" alt="Presenter" />
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
			src="{base}/images/{photo}.{isPng ? 'png' : 'jpg'}"
			srcset="{base}/images/{photo}.{isPng ? 'png' : 'jpg'} 1x, {base}/images/{photo}@2x.{isPng ? 'png' : 'jpg'} 2x"
			alt="Presenter"
		/>
	</picture>
{/if}
