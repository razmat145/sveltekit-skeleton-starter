<script>
	import { AppRail, AppRailAnchor, AppRailTile } from '@skeletonlabs/skeleton';
	import { initializeStores, Drawer, getDrawerStore } from '@skeletonlabs/skeleton';

	initializeStores();
	const drawerStore = getDrawerStore();

	let group = 0;
	let toggled = false;

	export const toggle = () => {
		toggled = !toggled;
	};

	$: if (toggled) {
		drawerStore.open();
	} else {
		drawerStore.close();
	}

	export function drawerClose() {
		toggled = false;
	}
</script>

<Drawer width="w-[15%]" on:backdrop={drawerClose}>
	<AppRail width="auto" aspectRatio="aspect-[2/0.5]">
		<AppRailTile bind:group name="Home" value={0} title="Home">
			<AppRailAnchor href="/" on:click={drawerClose}>Home</AppRailAnchor>
		</AppRailTile>
		<AppRailTile bind:group name="tile-2" value={1} title="tile-2">
			<AppRailAnchor href="/page-one" on:click={drawerClose}>Page One</AppRailAnchor>
		</AppRailTile>
		<AppRailTile bind:group name="tile-3" value={2} title="tile-3">
			<AppRailAnchor href="/page-two" on:click={drawerClose}>Page two</AppRailAnchor>
		</AppRailTile>
	</AppRail>
</Drawer>
