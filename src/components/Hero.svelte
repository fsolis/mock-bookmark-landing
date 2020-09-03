<script>
  import ImageHero from "./ImageHero.svelte";
</script>

<style type="text/scss">
  @import "../styles/styles";

  .hero {
    display: flex;
    flex-direction: column-reverse;
    justify-content: space-between;
    margin: 1rem;

    @include medium {
      flex-direction: row;
    }

    &__left {
      display: flex;
      flex-direction: column;
      flex: 1;
      padding: 1rem;
      margin: auto;
      text-align: center;

      @include medium {
        flex: 2;
        text-align: start;
      }
    }

    &__right {
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
        z-index: 1;

        @include medium {
          top: 30%;
        }
      }
    }

    &__img {
      position: relative;
      height: 180px;
      width: auto;
      margin: auto;
      z-index: 2;

      @include small {
        height: 240px;
      }

      @include small-medium {
        height: 300px;
      }

      @include medium {
        height: 100%;
      }
    }

    &__title {
      color: $drk-blue;
    }

    &__description {
      color: $grey-blue;
      font-weight: $font-semi-bold;
      line-height: 2.15rem;
      margin-bottom: 2rem;
    }
  }

  .hero-btn-row {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    &__btn {
      margin-bottom: 1rem;
      max-width: 250px;
    }

    @include medium {
      flex-direction: row;
      justify-content: flex-start;

      &__btn {
        margin-bottom: 0;
        &:first-of-type {
          margin-right: 1rem;
        }
      }
    }
  }

  :global(.img-hero > .main-img-hero) {
    position: relative;
    height: 180px;
    width: auto;
    margin: auto;
    z-index: 2;

    @include small {
      height: 240px;
    }

    @include small-medium {
      height: 300px;
    }

    @include medium {
      height: 100%;
    }
  }
</style>

<section class="hero">
  <div class="hero__left">
    <h1 class="hero__title">A Simple Bookmark Manager</h1>
    <p class="hero__description">
      A clean and simple interface to organize your favourite websites. Open a
      new browser tab and see your sites load instantly. Try it for free.
    </p>
    <div class="hero-btn-row">
      <button class="btn btn--blue hero-btn-row__btn">Get it on Chrome</button>
      <button class="btn hero-btn-row__btn">Get it on Firefox</button>
    </div>
  </div>
  <ImageHero directionRight={true}>
    <img
      class="main-img-hero"
      src="../assets/illustration-hero.svg"
      alt="Boomkark Page Layout" />
  </ImageHero>
</section>
