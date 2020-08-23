<style type="text/scss">
  @import "../styles/styles";
  .page-header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    flex-grow: 1;
    margin: 1rem;

    &__logo {
      margin: auto 0;
      height: 30px;
    }
  }

  .nav {
    &__btn {
      background-color: white;
      color: $drk-blue;
      padding: 10px;
      font-weight: $font-weight;
      letter-spacing: 2px;
      width: 125px;
      text-transform: uppercase;

      &--red {
        background-color: $primary-red;
        color: white;

        &:active,
        &:focus {
          color: $primary-red;
          background-color: white;
          box-shadow: none;
          border: 1px solid $primary-red;
        }
      }
    }
  }
</style>

<header class="page-header">
  <img
    class="page-header__logo"
    src="./assets/logo-bookmark.svg"
    alt="Bookmark Logo" />

  <div class="nav">
    <button class="nav__btn btn btn--no-bg">Features</button>
    <button class="nav__btn btn btn--no-bg">Pricing</button>
    <button class="nav__btn btn btn--no-bg">Contact</button>
    <button class="nav__btn nav__btn--red btn">Login</button>
  </div>
</header>
