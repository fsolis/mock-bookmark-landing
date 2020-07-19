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
    margin: 2rem;
    padding: 2rem;

    &__heading {
      color: $drk-blue;
    }

    &__desc {
      color: $grey-blue;
    }

    &__divider {
      border: none;
      border-bottom: 4px dotted $grey-blue;
    }

    > .btn {
      padding: 1rem 2.25rem;
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
      <img src="../assets/logo-chrome.svg" alt="Chrome logo" />
      <h3 class="extension__heading">Add to Chrome</h3>
      <p class="extension__desc">Minimum version 62</p>
      <hr class="extension__divider" />
      <button class="btn btn--blue">Add & Install Extension</button>
    </div>
    <div class="extension">
      <img src="../assets/logo-firefox.svg" alt="Firefox logo" />
    </div>
  </div>

</section>
