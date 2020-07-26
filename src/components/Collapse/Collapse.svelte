<script context="module">
  export const COLLAPSE_ITEMS = {};
</script>

<script>
  import { setContext, onDestroy } from "svelte";
  import { writable } from "svelte/store";

  const collapseItems = [];
  const selectedItem = writable(null);
  let className;
  export { className as class };

  setContext(COLLAPSE_ITEMS, {
    registerItem: item => {
      // Add item to list of collapseItems
      collapseItems.push(item);

      onDestroy(() => {
        const i = collapseItems.indexOf(item);
        // Remove item from item list
        collapseItems.splice(i, 1);
        // If the current item is being destroyed then we set the current
        // item to the item at the same item index, unless it's the last
        // one then we do the one before
        selectedItem.update(current => null);
      });
    },
    selectItem: item => {
      if (!item) return selectedItem.set(null);

      const i = collapseItems.indexOf(item);
      selectedItem.set(item);
    },
    selectedItem
  });
</script>

<div class={`collapse ${className || ''}`}>
  <slot />
</div>
