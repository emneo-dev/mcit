<script lang="ts">
  import type { UserInfo } from '$lib/UserInfo';
  import raw_tree from './users.json';
  import User from '$lib/User.svelte';

  const tree = raw_tree as UserInfo['invited'];
</script>

<main class="absolute inset-0 flex flex-col items-center p-8">
  <h1 class="text-5xl font-bold">KreogMC</h1>
  {#if Object.keys(tree).length !== 0}
    <ul class="flex grow items-center">
      {#each Object.entries(tree) as [username, info]}
        <User {username} {info} />
      {/each}
    </ul>
  {:else}
    <span class="flex grow items-center text-2xl">No players registered in users.json!</span>
  {/if}
</main>
