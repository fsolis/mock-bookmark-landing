<style type="text/scss">
  @import "../styles/styles";

  .hero {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    margin: 1rem;

    &__left {
      display: flex;
      flex-direction: column;
      flex-grow: 2;
      padding: 1rem;
      margin: auto;
    }

    &__right {
      display: flex;
      flex-grow: 4;
      position: relative;
    }

    &__img {
      position: relative;
      right: -3rem;
      bottom: -3rem;
      height: auto;
      width: 800px;
    }

    &__title {
      color: $drk-blue;
      font-size: 3.25rem;
      margin-bottom: 0;
    }

    &__description {
      color: $grey-blue;
      font-size: 1.25rem;
      font-weight: $font-semi-bold;
      line-height: 2.15rem;
      margin-bottom: 2rem;
    }
  }

  .hero-btn-row {
    display: flex;
    flex-direction: row;

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
  <div class="hero__right background-decorator--right">
    <img
      class="hero__img"
      src="../assets/illustration-hero.svg"
      alt="Boomkark Page Layout" />
  </div>
</section>
