<script lang="ts">
	import Button from '$lib/components/Button.svelte';
	import type { Action } from 'svelte/action';

	const typewriter: Action = (node: HTMLElement) => {
		const children = Array.from(node.children).filter((e) => e.tagName !== 'BR');

		let charIndex = 0;
		
		for (let i = 0; i < children.length; i++) {
			const child = children[i];

			if (!child.textContent) continue;

			let textContent = child.textContent;
			child.textContent = '';

			for (let j = 0; j < textContent.length; j++) {
				const char = textContent.charAt(j);

				const span = document.createElement('span');
				span.innerText = char;
				span.style = `--i: ${charIndex}`;
				span.style.opacity = '0';
				span.classList.add('typewrited');
				child.appendChild(span);

				charIndex++;
			}
		}
	};
</script>

<section class="hero">
	<div class="wrapper">
		<div class="text-container">
			<h1 use:typewriter>
				<span>Lorem ipsum&nbsp;</span><b>dolor sit.</b><br /><span>Amet consectetur elit.</span>
			</h1>
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque unde vel fugit! Nemo, facere
				maxime!
			</p>
			<div class="button-group">
				<Button filled>Lorem, ipsum.</Button><Button>Lorem, ipsum.</Button>
			</div>
		</div>
		<div class="image-container"></div>
	</div>
</section>

<style lang="scss">
	@use '#styles/variables' as *;

	section {
		padding-top: calc(55px + 15px + 50px);
		padding-bottom: 50px;

		.wrapper {
			display: grid;
			grid-template-columns: auto auto;
			padding: 0 30px;
			gap: 20px;
		}

		.text-container {
			display: grid;
			place-content: center;

			& > h1 {
				font-size: 2.5em;
				line-height: 1.3;
				margin-bottom: 20px;

				b {
					color: $lime-green;
				}

				:global(span.typewrited) {
					animation-name: typewrited;
					animation-duration: 0s;
					animation-delay: calc(var(--i) * .05s);
					animation-fill-mode: forwards;
				}
			}

			& > p {
				line-height: 1.7;
				color: rgb(60, 60, 60);
			}
		}

		.image-container {
			aspect-ratio: 1/1;
			background-color: $lime-green;
			padding: 30px;
			min-height: 500px;
		}

		.button-group {
			display: flex;
			gap: 10px;
			flex-wrap: wrap;
		}
	}

	@keyframes typewrited {
		from {
			opacity: 0;
		}

		to {
			opacity: 1;
		}
	}
</style>
