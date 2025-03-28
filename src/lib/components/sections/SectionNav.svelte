<script lang="ts">
	import type { Snippet } from 'svelte';
	import Asterisk from '../icons/Asterisk.svelte';

	const { children, dark = false }: { children: Snippet, dark?: boolean } = $props();
</script>

<p><Asterisk {dark} />{@render children()}</p>

<style lang="scss">
	p {
		color: rgba(0, 0, 0, 0.5);
		text-transform: uppercase;
		letter-spacing: 1px;
		margin-bottom: 10px;
    display: flex;
    gap: 5px;
    align-items: center;
	}
</style>
