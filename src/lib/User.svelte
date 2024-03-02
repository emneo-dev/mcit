<script lang="ts">
	import type { UserInfo } from './UserInfo';

	export let username: string;
	export let info: UserInfo;
</script>

<li>
	<span class="font-mono text-xl">
		{username}
	</span>
	{#if Object.keys(info.invited).length !== 0}
		<ul class="ml-1 border-l border-l-slate-400 pl-3 dark:border-l-slate-600">
			{#each Object.entries(info.invited) as [username, new_info]}
				<svelte:self {username} info={new_info} />
			{/each}
		</ul>
	{/if}
</li>
