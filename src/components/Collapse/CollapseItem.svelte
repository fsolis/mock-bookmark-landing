<script>
  import { getContext } from "svelte";
  import { COLLAPSE_ITEMS } from "./Collapse.svelte";
  import { slide } from "svelte/transition";
  import { quintOut } from "svelte/easing";

  const item = {};
  const { registerItem, selectItem, selectedItem } = getContext(COLLAPSE_ITEMS);

  registerItem(item);

  export let title;
  let currentItem;
  selectedItem.subscribe((item) => (currentItem = item));

  const handleClick = () => {
    if (currentItem === item) {
      selectItem(null);
      return;
    }
    selectItem(item);
  };
</script>

<style type="text/scss">
  @import "../../styles/styles";
  .collapse-item {
    &__heading {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      cursor: pointer;
    }

    &:hover {
      .collapse-item__heading > p {
        color: $primary-red;
      }
    }

    &__img {
      min-width: 30px;
      height: 30px;
      width: 30px;
      align-self: center;

      &--expanded {
        transform: scaleY(-1);
        color: $primary-red;
      }
    }
  }
</style>

<div class="collapse-item" on:click={handleClick}>
  <div class="collapse-item__heading">
    <p>{title}</p>
    {#if $selectedItem === item}
      <img
        class="collapse-item__img collapse-item__img--expanded"
        src="../assets/icon-arrow-red.svg"
        alt="Expand Collapse Arrow" />
    {/if}
    {#if $selectedItem !== item}
      <img
        class:collapse-item__img--expanded={$selectedItem === item}
        class="collapse-item__img"
        src="../assets/icon-arrow.svg"
        alt="Expand Collapse Arrow" />
    {/if}
  </div>
  {#if $selectedItem === item}
    <div
      transition:slide={{ delay: 25, duration: 300, easing: quintOut }}
      class="collapse-item__panel">
      <slot />
    </div>
  {/if}
</div>
