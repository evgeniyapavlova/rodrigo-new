<script>
	import AllBlocks from '$comps/AllBlocks.svelte';
	// import meta_img from '$lib/images/meta__img__en.jpg';

	const title = 'IQ Option - Rodrigo Trader';
	const desc =
		'¿Quieres llevar tu trading al siguiente nivel y contar con el respaldo de señales precisas cada día? En mi canal de Telegram comparto análisis y estrategias listas para aplicar, disponibles desde la mañana hasta la noche, de lunes a domingo';
</script>

<svelte:head>
	<title>{title}</title>
	<meta name="description" content={desc} />
	<meta property="og:title" content={title} />
	<meta property="og:description" content={desc} />
	<!-- <meta property="og:image" content={meta_img} /> -->
	<meta name="twitter:card" content="summary_large_image" />
	<meta name="twitter:title" content={title} />
	<meta name="twitter:description" content={desc} />
	<!-- <meta name="twitter:image" content={meta_img} /> -->
</svelte:head>

<AllBlocks />
