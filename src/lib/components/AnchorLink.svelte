<script lang="ts">
	import type { Snippet } from 'svelte';
	import LinkIcon from './icons/LinkIcon.svelte';

	const { href, children }: { href: string; children: Snippet } = $props();
</script>

<a {href} class="anchor-link"><LinkIcon /><span>{@render children()}</span></a>

<style lang="scss">
	@use '#styles/variables' as *;

  a {
		display: flex;
		color: $lime-green;
    align-items: center;
    gap: 7px;
    text-decoration: underline;
		width: fit-content;
		
    & > :global(svg) {
			height: 1em;
		}

    span {
      letter-spacing: .8px;
    }
	}
</style>
