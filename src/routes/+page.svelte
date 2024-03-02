<script lang="ts">
	import type { UserInfo } from '$lib/UserInfo';
	import raw_tree from './users.json';
	import User from '$lib/User.svelte';

	const tree = raw_tree as UserInfo['invited'];
</script>

<main class="absolute inset-0 flex flex-col items-center p-8">
	<h1 class="text-5xl font-bold">KreogMC</h1>
	<ul class="flex grow items-center">
		<User username="huntears" info={tree.huntears} />
	</ul>
</main>
