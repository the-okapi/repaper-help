<script lang="ts">
	import { goto } from '$app/navigation';
	import { page } from '$app/state';
	import { mode, setMode } from 'mode-watcher';

	let { children, light = 'Light', dark = 'Dark' } = $props();

	function setLight() {
		setMode('light');
	}

	function setDark() {
		setMode('dark');
	}

	function english() {
		goto('/en');
	}

	function french() {
		goto('/fr');
	}
</script>

<div class="fixed top-0 flex h-20 w-screen border-b border-(--o) bg-(--bg) p-5">
	<div class="flex w-full items-center">
		{@render children()}
	</div>
	<h1 class="flex items-center px-5 text-4xl font-bold whitespace-nowrap">{page.data.title}</h1>
	<div class="flex w-full items-center justify-end gap-5">
		<p class="flex text-lg">
			{#if mode.current === 'dark'}
				<button class="under cursor-pointer" onclick={setLight}>{light}</button>
				/
				<span class="cursor-default font-bold">{dark}</span>
			{:else}
				<span class="cursor-default font-bold">{light}</span>
				/
				<button class="under cursor-pointer" onclick={setDark}>{dark}</button>
			{/if}
		</p>
		<p class="flex text-lg">
			{#if page.route.id?.includes('/fr')}
				<button class="under cursor-pointer" onclick={english}>En</button>
				/
				<span class="cursor-default font-bold">Fr</span>
			{:else}
				<span class="cursor-default font-bold">En</span>
				/
				<button class="under cursor-pointer" onclick={french}>Fr</button>
			{/if}
		</p>
	</div>
</div>
<div class="h-20"></div>

<style>
	.under:hover {
		text-decoration: underline 1.5px;
	}
</style>
