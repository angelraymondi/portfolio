<script lang="ts">
	import type { Snippet } from 'svelte';

	const { children, filled = false }: { children: Snippet; filled?: boolean } = $props();
</script>

<button class={filled ? 'filled' : undefined}>{@render children()}</button>

<style lang="scss">
	@use 'sass:color';
	@use './../../styles/variables' as *;

	button {
		padding: 13px 23px;
		margin: 20px 0;
		background: transparent;
		font-size: 1em;
		border: 1px solid black;
		border-radius: 10px;
		font-weight: 500;
		cursor: pointer;
		transition:
			box-shadow cubic-bezier(0.165, 0.84, 0.44, 1) 0.5s,
			transform cubic-bezier(0.165, 0.84, 0.44, 1) 0.5s;

		&:hover {
			box-shadow: 0px 4px 15px color.scale(rgb(151, 151, 151), $alpha: -60%);
		}

		&:active {
			transform: scale(0.97);
		}
	}

	button.filled {
		padding: 13px 23px;
		margin: 20px 0;
		background-color: $lime-green;
		font-size: 1em;
		border: none;
		border-radius: 10px;
		font-weight: 500;
		cursor: pointer;

		&:hover {
			box-shadow: 0px 4px 15px color.scale($lime-green, $alpha: -25%);
		}
	}
</style>
