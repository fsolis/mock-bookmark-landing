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
      }
    }

    &__img {
      position: relative;
      height: auto;
      width: 80%;
      margin: auto;
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
    flex-direction: row;
    justify-content: center;

    @include medium {
      justify-content: flex-start;
    }

    &__btn {
      &:first-of-type {
        margin-right: 1rem;
      }
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
  <div class="hero__right">
    <img
      class="hero__img"
      src="../assets/illustration-hero.svg"
      alt="Boomkark Page Layout" />
  </div>
</section>
