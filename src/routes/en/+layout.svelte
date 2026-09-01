<script lang="ts">
	import NavBar from '$lib/NavBar.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<title>Repaper Help</title>
</svelte:head>

<NavBar>
	<a href="/en">Home</a>
</NavBar>

<div class="p-5">
	{@render children()}
</div>

<style>
	a:hover {
		text-decoration: underline 1.5px;
	}
</style>
