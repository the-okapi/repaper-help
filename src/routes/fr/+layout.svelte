<script lang="ts">
	import NavBar from '$lib/NavBar.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<title>Aide Repaper</title>
</svelte:head>

<NavBar light="Clair" dark="Sombre">
	<a href="/fr">Accueil</a>
</NavBar>

<div class="p-5">
	{@render children()}
</div>

<style>
	a:hover {
		text-decoration: underline 1.5px;
	}
</style>
