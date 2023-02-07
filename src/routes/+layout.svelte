        

<script lang="ts">
  import { page } from "$app/stores"
</script>

{#if $page.data.session}
   
          <span>
            <small>Signed in as</small><br />
            <strong
              >{$page.data.session.user?.email ??
                $page.data.session.user?.name}</strong
            >
          </span>
          <a href="/auth/signout" class="button" data-sveltekit-preload-data="off">Sign out</a>
            <slot />
        {:else}
          <span >You are not signed in</span>
          <a href="/auth/signin" data-sveltekit-preload-data="off">Sign in</a>
        {/if}