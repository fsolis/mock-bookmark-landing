<script>
  export let directionRight = true;
  console.log(directionRight);
</script>

<style type="text/scss">
  @import "../styles/styles";

  :global(.img-hero-right) {
    display: flex;
    flex: 1;
    position: relative;

    @include medium {
      flex: 3;
      height: 185px;
      margin: auto 0;
    }

    @media screen and (min-width: 750px) {
      height: 225px;
    }

    @include large {
      height: 300px;
    }

    &:after {
      position: absolute;
      content: "";
      width: 100%;
      height: 80%;
      background-color: $primary-blue;
      border-radius: 0 0 0 25%;
      top: 35%;
      left: 40%;
      z-index: -1;

      @include medium {
        top: 30%;
      }
    }
  }

  :global(.img-hero-left) {
    display: flex;
    flex: 1;
    position: relative;

    @include medium {
      flex: 3;
      height: 185px;
      margin: auto 0;
    }

    @media screen and (min-width: 750px) {
      height: 225px;
    }

    @include large {
      height: 300px;
    }

    &:after {
      position: absolute;
      content: "";
      width: 100%;
      height: 80%;
      background-color: $primary-blue;
      border-radius: 0 0 25% 0;
      right: 40%;
      top: 35%;
      z-index: -1;

      @include medium {
        top: 30%;
      }
    }
  }
</style>

<div
  class="img-hero"
  class:img-hero-left={!directionRight}
  class:img-hero-right={directionRight}>
  <slot />
</div>
