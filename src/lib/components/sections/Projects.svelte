<script lang="ts">
	import ChatMatIcon from '$lib/components/icons/projects/ChatMatIcon.svelte';
	import AnchorLink from '../AnchorLink.svelte';
	import SectionNav from './SectionNav.svelte';

	const projects = [
		{
			icon: ChatMatIcon,
			title: 'ChatMAT',
			description: 'ChatMAT es un sitio web dedicado a asesorar alumnos. Para realizar el sitio empleé mis conocimientos en Svelte 5 y self-hosting.',
			anchor: {
				href: 'https://www.chatmat.net.pe',
				text: 'www.chatmat.net.pe'
			}
		},
		{
			icon: ChatMatIcon,
			title: 'ChatMAT',
			description: 'ChatMAT es un sitio web dedicado a asesorar alumnos. Para realizar el sitio empleé mis conocimientos en Svelte 5 y self-hosting.',
			anchor: {
				href: 'https://www.chatmat.net.pe',
				text: 'www.chatmat.net.pe'
			}
		},
		{
			icon: ChatMatIcon,
			title: 'ChatMAT',
			description: 'ChatMAT es un sitio web dedicado a asesorar alumnos. Para realizar el sitio empleé mis conocimientos en Svelte 5 y self-hosting.',
			anchor: {
				href: 'https://www.chatmat.net.pe',
				text: 'www.chatmat.net.pe'
			}
		},
		{
			icon: ChatMatIcon,
			title: 'ChatMAT',
			description: 'ChatMAT es un sitio web dedicado a asesorar alumnos. Para realizar el sitio empleé mis conocimientos en Svelte 5 y self-hosting.',
			anchor: {
				href: 'https://www.chatmat.net.pe',
				text: 'www.chatmat.net.pe'
			}
		}
	];
</script>

<section>
	<div class="wrapper">
		<SectionNav inherit>Proyectos</SectionNav>
		<h1>Proyectos en los que colaboré</h1>
		<p>Lorem ipsum dolor sit amet consectetur, adipisicing elit. Aliquam, nobis. Sit, at vero.</p>

		<div class="container">
			{#each projects as project}
				<div class="project">
					<div>
						<svelte:component this={project.icon} />
					</div>
					<h1>{project.title}</h1>
					<p>{project.description}</p>
					<AnchorLink href={project.anchor.href}>{project.anchor.text}</AnchorLink>
				</div>
			{/each}
		</div>
	</div>
</section>

<style lang="scss">
	@use '#styles/variables' as *;
	@use 'sass:color';

	section {
		background-color: rgb(20, 20, 20);
	}

	section > .wrapper {
		padding: 50px 30px;
		background-size: 500px;
		color: color.mix($lime-green, white, 33.33%);

		& > h1 {
			font-size: 2em;
			margin-bottom: 20px;
			letter-spacing: 1px;
			color: $lime-green;
		}
	}

	.container {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(30ch, 1fr));
		gap: 15px;
		margin-top: 20px;

		.project {
			border: 1px solid rgba(255, 255, 255, 0.07);
			padding: 25px;
			border-radius: 15px;
			display: flex;
			flex-direction: column;

			h1 {
				margin: 15px 0 7px 0;
				font-size: 2em;
			}

			p {
				line-height: 1.7;
				margin-bottom: 15px;
			}

			:global(a.anchor-link) {
				margin-top: auto;
			}
		}
	}
</style>
