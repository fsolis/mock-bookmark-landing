<style type="text/scss">
  @import "../../styles/styles";

  .tab-list {
    display: flex;
    flex-direction: column;
    justify-content: center;

    @include medium {
      flex-direction: row;
    }
  }
</style>

<div class="tab-list">
  <slot />
</div>
