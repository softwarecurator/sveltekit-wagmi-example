<script lang="ts">
  import { defaultConfig, wagmiLoaded } from "svelte-wagmi";
  import { onMount } from "svelte";
  import {
    PUBLIC_ALCHEMY_KEY,
    PUBLIC_WALLETCONNECT_PROJECTID,
  } from "$env/static/public";

  onMount(async () => {
    const erckit = defaultConfig({
      appName: "erc.kit",
      walletConnectProjectId: PUBLIC_WALLETCONNECT_PROJECTID,
      alchemyId: PUBLIC_ALCHEMY_KEY,
    });

    await erckit.init();
  });
</script>

{#if $wagmiLoaded}
  <slot />
{/if}
