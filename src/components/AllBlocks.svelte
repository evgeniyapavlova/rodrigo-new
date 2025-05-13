<script>
	import { base } from '$app/paths';
	import { searchString } from '$lib/stores/affs';
	import Photo from './Photo.svelte';
	import TelegramLogo from './TelegramLogo.svelte';
	import Counter from './Counter.svelte';
	import Footer from './Footer.svelte';
	import Labels from './Labels.svelte';
	import Header from './Header.svelte';
</script>

<Header />

<section>
	<div class="content">
		<div class="content-photos">
			<div class="flare"></div>
			<div class="content-photos-left">
				<Photo photo="photo1" />
			</div>

			<div class="content-photos-right">
				{#each [2, 3] as i}
					<div class="photo-wrap">
						<Photo photo="photo{i}" />
					</div>
				{/each}
			</div>
			<Labels />
		</div>
		<div class="content-text">
			<h1 class="heading">Rodrigo Trader</h1>
			<p>
				¿Quieres llevar tu trading al siguiente nivel y contar con el respaldo de señales precisas
				cada día? En mi canal de Telegram comparto análisis y estrategias listas para aplicar,
				disponibles desde la mañana hasta la noche, de lunes a domingo.<br />Al unirte, no solo
				recibirás señales y oportunidades del mercado: también accederás a conocimientos
				adicionales, estarás rodeado de personas con tus mismos intereses y contarás con la guía de
				un experto para mejorar tus decisiones. Es tu espacio para aprender, compartir y avanzar con
				seguridad.<br />Únete ahora y forma parte de una comunidad enfocada en crecer, aprender y
				alcanzar resultados financieros sólidos.
			</p>
			<h2 class="heading" style="margin: 40px 0 20px;">Aprenderás:</h2>
			<div class="list">
				<div class="with-icon">
					<div class="icon">
						<img src="{base}/images/icon1.svg" alt="" />
					</div>
					Tutoriales paso a paso sobre IQ Option.
				</div>
				<div class="with-icon">
					<div class="icon">
						<img src="{base}/images/icon2.svg" alt="" />
					</div>
					Estrategias poderosas para novatos y traders experimentados.
				</div>
			</div>
			<div class="cta-block cta-block-1">
				<a
					href="https://iqoption.com/en/register{$searchString}"
					class="button button-small button-primary">Registro</a
				>
				<a href="https://t.me/rodrigosalario" class="button button-small button-secondary"
					><TelegramLogo /><span>Suscribirse</span></a
				>
			</div>
		</div>
	</div>
</section>

<Counter />
<Footer />
