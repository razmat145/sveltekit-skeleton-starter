<script lang="ts">
	import { AppBar } from '@skeletonlabs/skeleton';
	import { createEventDispatcher } from 'svelte';

	const dispatch = createEventDispatcher();

	function handleMenuClick() {
		dispatch('menu-click');
	}
</script>

<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
	<svelte:fragment slot="lead">
		<button on:click={handleMenuClick} type="button" class="btn-icon variant-filled">
			<svg xmlns="http://www.w3.org/2000/svg" width="2em" height="2em" viewBox="0 0 24 24"
				><path
					fill="currentColor"
					d="M20 10.75H4a.75.75 0 0 1 0-1.5h16a.75.75 0 0 1 0 1.5m0-4H4a.75.75 0 0 1 0-1.5h16a.75.75 0 0 1 0 1.5m0 8H4a.75.75 0 0 1 0-1.5h16a.75.75 0 0 1 0 1.5m0 4H4a.75.75 0 0 1 0-1.5h16a.75.75 0 0 1 0 1.5"
				/></svg
			>
		</button>
	</svelte:fragment>
	<h1 class="h1">
		<span
			class="bg-gradient-to-br from-blue-500 to-black bg-clip-text text-transparent box-decoration-clone"
			>Your Title Here</span
		>
	</h1>
	<svelte:fragment slot="trail">
		<a
			class="btn btn-sm variant-ghost-surface"
			href="notfound"
			target="_blank"
			rel="noreferrer"
		>
			Discord
		</a>
		<a
			class="btn btn-sm variant-ghost-surface"
			href="notfound"
			target="_blank"
			rel="noreferrer"
		>
			Twitter
		</a>
		<a
			class="btn btn-sm variant-ghost-surface"
			href="notfound"
			target="_blank"
			rel="noreferrer"
		>
			GitHub
		</a>
	</svelte:fragment>
</AppBar>
