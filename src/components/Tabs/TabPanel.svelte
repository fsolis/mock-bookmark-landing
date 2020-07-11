<script>
  import { getContext } from "svelte";
  import { TABS } from "./Tabs.svelte";

  const panel = {};
  const { registerPanel, selectedPanel } = getContext(TABS);

  registerPanel(panel);
</script>

<style>
  .tab-panel {
    display: flex;
    flex-direction: row;
  }
</style>

{#if $selectedPanel === panel}
  <div class="tab-panel">
    <slot />
  </div>
{/if}
