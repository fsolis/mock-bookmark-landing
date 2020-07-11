<script context="module">
  export const TABS = {};
</script>

<script>
  import { setContext, onDestroy } from "svelte";
  import { writable } from "svelte/store";

  const tabs = [];
  const panels = [];
  const selectedTab = writable(null);
  const selectedPanel = writable(null);

  setContext(TABS, {
    registerTab: tab => {
      // Add tab to list of tabs
      tabs.push(tab);
      // If a tab is already selected keep it as selected otherwise
      // default to this new one
      selectedTab.update(current => current || tab);

      onDestroy(() => {
        const i = tabs.indexOf(tab);
        // Remove tab from tab list
        tabs.splice(i, 1);
        // If the current tab is being destroyed then we set the current
        // tab to the tab at the same tab index, unless it's the last
        // one then we do the one before
        selectedTab.update(current =>
          current === tab ? tabs[i] || tabs[tabs.length - 1] : current
        );
      });
    },
    registerPanel: panel => {
      // Add panel to panels list
      panels.push(panel);
      // If no current panel is selected then we set the this panel
      // as current
      selectedPanel.update(current => current || panel);

      onDestroy(() => {
        const i = panels.indexOf(panel);
        // Remove panel from panels list
        panels.splice(i, 1);
        // If the current active panel is being destroyed then we set
        // the panel at the same index as the current, otherwise if the
        // panel that was destoryed is the last one then we set the one
        // before as the current panel
        selectedPanel.update(current =>
          current === panel ? panels[i] || panels[panels.length - 1] : current
        );
      });
    },
    selectTab: tab => {
      const i = tabs.indexOf(tab);
      selectedTab.set(tab);
      selectedPanel.set(panels[i]);
    },
    selectedTab,
    selectedPanel
  });
</script>

<div class="tabs">
  <slot />
</div>
