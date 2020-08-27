<script>
  import { getContext } from "svelte";
  import { TABS } from "./Tabs.svelte";

  const tab = {};
  const { registerTab, selectTab, selectedTab } = getContext(TABS);

  registerTab(tab);
</script>

<style type="text/scss">
  @import "../../styles/styles";

  .tab {
    background-color: transparent;
    border: none;
    padding: 1.75rem 3rem;
    color: $grey-blue;
    font-weight: $font-semi-bold;
    border-bottom: 1px solid $light-grey;
    cursor: pointer;
    position: relative;

    &:first-of-type {
      border-top: 1px solid $light-grey;
    }

    @include medium {
      &:first-of-type {
        border-top: none;
      }

      &:active,
      &:focus {
        outline: none;
        border: none;
        border-bottom: 4px solid $primary-red;
      }

      &__selected {
        &::after {
          display: none;
        }
        border-bottom: 4px solid $primary-red;
      }
    }

    &__selected {
      &::after {
        content: "";
        position: absolute;
        width: 200px;
        height: 6px;
        background-color: $primary-red;
        bottom: 0;
        left: calc(50% - #{100px});
      }
    }

    &:hover {
      color: $primary-red;
    }
  }
</style>

<button
  class="tab"
  class:tab__selected={$selectedTab === tab}
  on:click={() => selectTab(tab)}>
  <slot />
</button>
