<script lang="ts">
	const { inherit }: { inherit: boolean } = $props();
</script>

<svg
	class={inherit ? 'inherit' : undefined}
	width="1em"
	height="1em"
	viewBox="0 0 24 24"
	fill="none"
	xmlns="http://www.w3.org/2000/svg"
>
	<path
		d="M12 4V20M19 7L5 17M5 7L19 17"
		stroke-width="2"
		stroke-linecap="round"
		stroke-linejoin="round"
	/>
</svg>

<style lang="scss">
	@use '#styles/variables' as *;

	svg > path {
		stroke: $lime-green;
	}

	svg.inherit > path {
		stroke: currentColor;
	}
</style>
