<script>
	import Footer from '$lib/components/Footer.svelte';
	import Header from '$lib/components/Header.svelte';
	import About from '$lib/components/sections/About.svelte';
	import Hero from '$lib/components/sections/Hero.svelte';
	import Projects from '$lib/components/sections/Projects.svelte';
	import Specialties from '$lib/components/sections/Specialties.svelte';
</script>

<Header></Header>
<main>
	<Hero></Hero>
	<div class="break"></div>
	<Specialties></Specialties>
	<About></About>
	<Projects></Projects>
	<Footer></Footer>
</main>

<svelte:head>
	<title>Angel Raymondi</title>
</svelte:head>

<style lang="scss">
	@use 'sass:color';
	@use '#styles/variables' as *;

	.break {
		height: 3em;
		background-color: $lime-green;
		background-image: linear-gradient(
				color.scale($lime-green, $alpha: -10%),
				color.scale($lime-green, $alpha: -10%)
			),
			url(/doodles/bombs.svg);
		background-size: cover;
		background-position: center;
	}
</style>
