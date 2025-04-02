<script lang="ts">
	import NodeJsIcon from '$lib/components/icons/NodeJsIcon.svelte';
	import SvelteIcon from '$lib/components/icons/SvelteIcon.svelte';
	import TypeScriptIcon from '$lib/components/icons/TypeScriptIcon.svelte';
	import HeartDoodle from '../doodles/HeartDoodle.svelte';
	import SectionNav from './SectionNav.svelte';
</script>

<section class="specialties wrappered">
	<SectionNav>Especialidades</SectionNav>
	<h1>
		<span>Mis</span><b>especialidades</b><span class="heart-doodle__container"><HeartDoodle /></span
		>
	</h1>
	<div class="container">
		<div>
			<NodeJsIcon fill="#9cf101"></NodeJsIcon>
			<h1>Node.js</h1>
			<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reprehenderit, eveniet.</p>
		</div>
		<div>
			<TypeScriptIcon fill="#9cf101"></TypeScriptIcon>
			<h1>TypeScript</h1>
			<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reprehenderit, eveniet.</p>
		</div>
		<div>
			<SvelteIcon fill="#9cf101"></SvelteIcon>
			<h1>Svelte</h1>
			<p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Reprehenderit, eveniet.</p>
		</div>
	</div>
</section>

<style lang="scss">
	@use '#styles/variables' as *;

	section {
		padding: 50px 30px;
		background-color: rgb(250, 250, 250);
		background-size: 500px;

		& > h1 {
			font-size: 2em;
			margin-bottom: 20px;
			letter-spacing: 1px;
			display: flex;
			gap: 10px;
			align-items: center;

			& > b {
				text-decoration-line: underline;
				text-decoration-thickness: 3px;
				color: $lime-green;
			}

			& > span.heart-doodle__container {
				display: flex;
				transform: translate(5px, -13px);
			}
		}

		.container {
			display: grid;
			grid-template-columns: repeat(auto-fit, minmax(30ch, 1fr));
			gap: 15px;

			& > div {
				background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.04), rgba(0, 0, 0, 0.06));
				padding: 25px;
				border-radius: 15px;
				display: flex;
				flex-direction: column;
				border: 1px solid rgba(0, 0, 0, .02);

				& > :global(svg) {
					margin-bottom: 15px;
				}

				p {
					color: rgba(0, 0, 0, 0.7);
					line-height: 1.7;
					margin-top: 7px;
				}
			}
		}
	}
</style>
