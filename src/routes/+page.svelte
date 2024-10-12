<script lang="ts">
  import { signIn, signOut } from "@auth/sveltekit/client"
  import { page } from "$app/stores"
</script>

{#if $page.data.session}
  <nav>
    <div>
      <img
        width="40px"
        src={$page.data.session?.user?.image ?? "https://i.pravatar.cc/300"}
        alt="User Avatar"
      />
      <strong>
        {$page.data.session?.user?.name}
      </strong>
    </div>
    <div>
      <button on:click={signOut}>sign out</button>
    </div>
  </nav>
{:else}
  <div>
    <img width="40px" src="/favicon.ico" alt="Company Logo" />
  </div>
  <div>
    <button on:click={signIn}>sign in</button>
  </div>
{/if}
<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>
