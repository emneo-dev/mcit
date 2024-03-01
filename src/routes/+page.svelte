<script lang="ts">
	import type { UserInfo } from '$lib/UserInfo';
	import raw_tree from './users.json';
	import User from '$lib/User.svelte';

	const tree = raw_tree as UserInfo["invited"];

</script>

<main class="absolute inset-0 flex items-center justify-center">
	<ul>
		<User username="huntears" info={tree.huntears} />
	</ul>
</main>
