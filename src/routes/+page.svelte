<script>
	import Header from '$lib/components/Header.svelte';
	import About from '$lib/components/sections/About.svelte';
	import Hero from '$lib/components/sections/Hero.svelte';
	import Specialties from '$lib/components/sections/Specialties.svelte';
</script>

<Header></Header>
<main>
  <Hero></Hero>
	<div class="break"></div>
  <Specialties></Specialties>
	<About></About>
</main>

<style lang="scss">
	@use 'sass:color';
	@use '#styles/variables' as *;

	.break {
		height: 3em;
		background-color: $lime-green;
	}
</style>
