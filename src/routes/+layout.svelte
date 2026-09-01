<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.png';
	import { ModeWatcher } from 'mode-watcher';

	let { children } = $props();
</script>

<ModeWatcher darkClassNames={['dark']} lightClassNames={['light']} defaultMode="system" />

<svelte:head><link rel="icon" href={favicon} /></svelte:head>
{@render children()}
