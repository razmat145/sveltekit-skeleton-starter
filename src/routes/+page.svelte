<script lang="ts">
	import Stats from '../lib/Stats.svelte';
	import { ProgressBar } from '@skeletonlabs/skeleton';

	const mockDataOne = [
		{
			title: 'Page views',
			stats: '456,133',
			description: '24% more than in the same month last year, 33% more that two years ago'
		},
		{
			title: 'New users',
			stats: '2,175',
			description: '13% less compared to last month, new user engagement up by 6%'
		},
		{
			title: 'Completed orders',
			stats: '1,994',
			description: '1994 orders were completed this month, 97% satisfaction rate'
		}
	];
	import { ProgressRadial } from '@skeletonlabs/skeleton';

	const mockdataTwo = [
		{
			label: 'Page views',
			stats: '456,578',
			progress: 65,
			color: 'stroke-primary-500',
			icon: 'up'
		},
		{
			label: 'New users',
			stats: '2,550',
			progress: 72,
			color: 'stroke-tertiary-500',
			icon: 'up'
		},
		{
			label: 'Orders',
			stats: '4,735',
			progress: 52,
			color: 'stroke-error-500',
			icon: 'down'
		}
	];
</script>

<div class="flex flex-col m-6">
	<div class="card p-6 m-6">
		<div class="text-xs opacity-50 text-white">MONTHLY GOAL</div>
		<div class="mb-4 text-2xl text-white">$7.49 / $10.00</div>
		<ProgressBar value={74.9} height="h-3" meter="bg-white" />
	</div>

	<div class="card p-6 flex justify-between gap-6 m-6">
		{#each mockDataOne as item, i}
			<div class="space-y-2 text-white">
				<div class="text-4xl">{item.stats}</div>
				<div class="uppercase">{item.title}</div>
				<div class="text-sm opacity-70">{item.description}</div>
			</div>
			{#if i < 2}
				<span class="divider-vertical !border-white max-h-full" />
			{/if}
		{/each}
	</div>

	<div class="grid grid-cols-1 md:grid-cols-3 gap-4 m-6">
		{#each mockdataTwo as stat}
			<div class="card p-6">
				<div class="flex space-x-5 items-center">
					<ProgressRadial value={stat.progress} stroke={125} meter={stat.color} width="w-20"
					></ProgressRadial>
					<div class="space-y-2">
						<div class="font-bold opacity-50 text-xs">{stat.label.toUpperCase()}</div>
						<div class="text-2xl font-bold">{stat.stats}</div>
					</div>
				</div>
			</div>
		{/each}
	</div>

	<Stats></Stats>
</div>
