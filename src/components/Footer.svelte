<script>
	import '$lib/styles/footer.scss';
	import Photo from './Photo.svelte';
	import TelegramLogo from './TelegramLogo.svelte';
	import { searchString } from '$lib/stores/affs';
</script>

<footer>
    <div class="footer-title heading">
        Rodrigo Trader
    </div>
	<Photo photo="footer/rodrigo-footer" hasMobile isPng />
	<div class="cta-block cta-block-2">
		<a href="https://iqoption.com/en/register{$searchString}" class="button button-primary button-large"
			>Registro</a
		>
		<a href="https://t.me/rodrigosalario" class="button button-secondary button-large"
			><TelegramLogo /><span>Suscribirse</span></a
		>
	</div>
</footer>
