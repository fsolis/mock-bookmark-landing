<style type="text/scss">
  @import "../styles/styles";
  .page-header {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    flex-grow: 1;
    margin: 25px 10%;

    &__logo {
      margin: auto 0;
      height: 30px;
    }
  }

  .nav {
    &__btn {
      background-color: white;
      color: $drk-blue;
      border: none;
      border-radius: 5px;
      padding: 10px;
      font-weight: $font-weight;
      width: 125px;

      &--red {
        background-color: $primary-red;
        color: white;
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
    <button class="nav__btn">Features</button>
    <button class="nav__btn">Pricing</button>
    <button class="nav__btn">Contact</button>
    <button class="nav__btn nav__btn--red">Login</button>
  </div>
</header>
