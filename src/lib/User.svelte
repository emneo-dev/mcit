<script lang="ts">
	import type { UserInfo } from './UserInfo';

	export let username: string;
	export let info: UserInfo;
</script>

<li>
	<span class="text-xl">
		{username}
	</span>
	{#if Object.keys(info.invited).length !== 0}
		<ul class="pl-4 border-l border-l-slate-400">
			{#each Object.entries(info.invited) as [username, new_info]}
				<svelte:self {username} info={new_info} />
			{/each}
		</ul>
	{/if}
</li>
