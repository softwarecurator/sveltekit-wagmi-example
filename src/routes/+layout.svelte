<script lang="ts">
  import { configureWagmi, wagmiLoaded } from "svelte-wagmi";
  import { onMount } from "svelte";

  onMount(async () => {
    await configureWagmi({
      walletconnect: true,
      walletconnectProjectID: "wallet-connect-project-id",
      alchemyKey: "alchemy-key",
      autoConnect: true,
    });
  });
</script>

{#if $wagmiLoaded}
  <slot />
{/if}
