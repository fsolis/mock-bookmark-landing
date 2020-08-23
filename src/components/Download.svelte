<style type="text/scss">
  @import "../styles/styles";
  .download {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    justify-content: center;
    text-align: center;
    margin: 4rem 0;

    &__header {
      color: $drk-blue;
    }

    &__sub-header {
      color: $grey-blue;
      max-width: 45%;
      margin: 0 auto;
      font-size: 1.25rem;
    }
  }

  .extensions {
    display: flex;
    flex-direction: row;
    flex-grow: 1;
    justify-content: center;
    padding: 3rem;
  }

  .extension {
    border-radius: 5px;
    box-shadow: 2px 2px 3px 2px transparentize($grey-blue, 0.8);
    height: fit-content;
    margin: 2rem;

    &:nth-of-type(2) {
      margin-top: 5rem;
    }

    &:nth-of-type(3) {
      margin-top: 8rem;
    }

    &__img {
      margin: 2rem 1rem;
    }

    &__heading {
      color: $drk-blue;
      margin-bottom: 0;
      margin-top: 0;
    }

    &__desc {
      color: $grey-blue;
      margin-bottom: 2rem;
    }

    &__divider {
      height: 4px;
      width: 100%;
    }

    > .btn {
      padding: 1rem 2.25rem;
      margin: 1.5rem;
    }
  }
</style>

<section class="download">
  <h1 class="download__header">Download the extension</h1>
  <p class="download__sub-header">
    We've got more browsers in the pipeline. Please do let us know if you've got
    a favorite you'd like us to prioritize.
  </p>
  <div class="extensions">
    <div class="extension">
      <img
        class="extension__img"
        src="../assets/logo-chrome.svg"
        alt="Chrome logo" />
      <h3 class="extension__heading">Add to Chrome</h3>
      <p class="extension__desc">Minimum version 62</p>
      <img
        class="extension__divider"
        src="../assets/bg-dots.svg"
        alt="Background Dots" />
      <button class="btn btn--blue">Add & Install Extension</button>
    </div>
    <div class="extension">
      <img
        class="extension__img"
        src="../assets/logo-firefox.svg"
        alt="Firefox logo" />
      <h3 class="extension__heading">Add to Firefox</h3>
      <p class="extension__desc">Minimum version 55</p>
      <img
        class="extension__divider"
        src="../assets/bg-dots.svg"
        alt="Background Dots" />
      <button class="btn btn--blue">Add & Install Extension</button>
    </div>
    <div class="extension">
      <img
        class="extension__img"
        src="../assets/logo-opera.svg"
        alt="Opera logo" />
      <h3 class="extension__heading">Add to Opera</h3>
      <p class="extension__desc">Minimum version 46</p>
      <img
        class="extension__divider"
        src="../assets/bg-dots.svg"
        alt="Background Dots" />
      <button class="btn btn--blue">Add & Install Extension</button>
    </div>
  </div>

</section>
