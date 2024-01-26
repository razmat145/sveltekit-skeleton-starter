<script lang="ts">
	import '../app.postcss';
	import '@fortawesome/fontawesome-free/css/all.min.css';

	import { AppShell, initializeStores } from '@skeletonlabs/skeleton';

	import AppTopBar from '$lib/AppTopBar.svelte';
	import AppNavBar from '$lib/AppNavBar.svelte';

	initializeStores();

	let toggleAppNavBar: () => void;
</script>

<AppShell>
	<svelte:fragment slot="header">
		<AppTopBar on:menu-click={toggleAppNavBar} />
	</svelte:fragment>

	<svelte:fragment slot="sidebarLeft">
		<AppNavBar bind:toggle={toggleAppNavBar} />
	</svelte:fragment>

	<slot />

	<svelte:fragment slot="pageFooter">Page Footer</svelte:fragment>
</AppShell>
