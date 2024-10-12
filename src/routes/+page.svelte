<script lang="ts">
  import { signIn, signOut } from "@auth/sveltekit/client"
  import { page } from "$app/stores"
</script>

{#if $page.data.session}
  <nav>
    <img
      src={$page.data.session?.user?.image ?? "https://i.pravatar.cc/300"}
      alt="User Avatar"
    />
  <button on:click={signOut}>sign out</button>
  </nav>
{:else}
  <div>
    <img src="/favicon.ico" alt="Company Logo" />
    <button on:click={signIn}>sign in</button>
  </div>
{/if}
<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
