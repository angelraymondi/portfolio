<script lang="ts">
	import type { Snippet } from 'svelte';
	import Asterisk from '../icons/Asterisk.svelte';

	const {
		children,
		inherit = false,
	}: { children: Snippet; inherit?: boolean } = $props();
</script>

<p><Asterisk {inherit} />{@render children()}</p>

<style lang="scss">
	p {
		color: rgba(0, 0, 0, 0.5);
		color: inherit;
		text-transform: uppercase;
		letter-spacing: 1px;
		margin-bottom: 10px;
		display: flex;
		gap: 5px;
		align-items: center;
	}
</style>
