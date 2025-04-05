<script lang="ts">
	import { onMount } from 'svelte';
	import GitHubIcon from './icons/GitHubIcon.svelte';
	import XIcon from './icons/XIcon.svelte';

	let sticked = $state(false);

	let nav: HTMLElement | null = null;

	function canBeStuck(computedStyles: CSSStyleDeclaration): boolean {
		return computedStyles.display !== 'none' && computedStyles.position === 'sticky';
	}

	function isStuck(
		el: HTMLElement,
		computedStyles: CSSStyleDeclaration,
		shouldUseBottomPosition: boolean
	): boolean {
		const offsetParent = el.offsetParent;
		if (!offsetParent) return false;
		const rect = el.getBoundingClientRect();

		if (shouldUseBottomPosition) {
			const elBottom = parseInt(computedStyles.bottom, 10);
			return window.innerHeight - rect.bottom <= elBottom;
		} else {
			const elTop = parseInt(computedStyles.top, 10);
			return rect.top <= elTop;
		}
	}

	function toggleClassIfStuck(el: HTMLElement) {
		const computedStyles = getComputedStyle(el);
		if (canBeStuck(computedStyles)) {
			const hasTopPositionSet = computedStyles.top !== 'auto';
			const hasBottomPositionSet = computedStyles.bottom !== 'auto';

			if (hasTopPositionSet || hasBottomPositionSet) {
				const stuck = isStuck(el, computedStyles, hasBottomPositionSet);
				el.classList.toggle('sticked', stuck);
			}
		}
	}

	onMount(() => {
		if (!nav) return;

		const onScroll = () => {
			if (!nav) return;
			toggleClassIfStuck(nav);
		};

		// Agrega el listener para el scroll
		window.addEventListener('scroll', onScroll);
		// Dispara el evento scroll inicialmente para la verificación
		window.dispatchEvent(new Event('scroll'));

		// Remueve el listener al destruir el componente
		return () => {
			window.removeEventListener('scroll', onScroll);
		};
	});
</script>

<nav bind:this={nav} class={['wrapper', sticked ? 'sticked' : undefined]}>
	<div>
		<h1>Angel Raymondi</h1>
	</div>
	<div>
		<ul class="social-media">
			<li><a href="https://github.com/angelraymondi" aria-label="GitHub"><GitHubIcon /></a></li>
			<li><a href="https://x.com/angelraymondii" aria-label="X"><XIcon /></a></li>
		</ul>
	</div>
	<!-- TODO: Completar -->
</nav>

<style lang="scss">
	nav {
		display: flex;
		justify-content: space-between;
		width: calc(100% - 30px);
		position: sticky;
		align-items: center;
		z-index: 50;
		margin: 0 auto;
		margin-top: 50px;
		top: 15px;

		h1 {
			font-size: 1.2em;
			font-weight: 400;
		}

		& > div {
			// background: rgba(0, 0, 0, 0.1);
			border: 1px solid rgba(0, 0, 0, 0.3);
			height: 55px;
			padding: 5px 20px;
			border-radius: 0.75em;
			display: flex;
			align-items: center;
			background-color: white;
			transition:
				backdrop-filter cubic-bezier(0.165, 0.84, 0.44, 1) 0.3s,
				background-color cubic-bezier(0.165, 0.84, 0.44, 1) 0.3s;
		}

		&.sticked > div {
			backdrop-filter: blur(20px);
			background-color: rgba(255, 255, 255, 0.6);
			border: 1px solid rgba(0, 0, 0, 0.09);
		}
	}

	ul.social-media {
		display: flex;
		align-items: center;
		gap: 15px;
		list-style: none;

		& > li > a {
			display: flex;
			align-items: center;
			justify-content: center;
			font-size: 1.2em;
		}
	}
</style>
