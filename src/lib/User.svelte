<script lang="ts">
	import type { UserInfo } from './UserInfo';

	export let username: string;
	export let info: UserInfo;
</script>

<li>
	<span class="text-xl font-mono">
		{username}
	</span>
	{#if Object.keys(info.invited).length !== 0}
		<ul class="pl-3 ml-1 border-l border-l-slate-400 dark:border-l-slate-600">
			{#each Object.entries(info.invited) as [username, new_info]}
				<svelte:self {username} info={new_info} />
			{/each}
		</ul>
	{/if}
</li>
