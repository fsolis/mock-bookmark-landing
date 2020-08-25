<script>
  import { writable } from "svelte/store";

  const menuOpenState = writable(false);

  const handleMenuClick = () => {
    menuOpenState.update((open) => !open);
  };
</script>

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
    display: none;

    @include large {
      display: block;
    }

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

  .mobile-nav-icon {
    display: flex;
    align-items: center;
    cursor: pointer;

    @include large {
      display: none;
    }

    > img {
      height: 20px;
    }
  }

  .mobile-nav {
    position: fixed;
    top: 0;
    bottom: 0;
    right: 0;
    left: 0;
    background-color: transparentize($drk-blue, 0.1);
    z-index: 100;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-between;

    &__heading {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 2rem;
    }

    &__close {
      height: 16px;
    }

    &__links {
      display: flex;
      flex-direction: column;
      flex: 1;
    }

    &__link {
      width: 100%;
      padding: 1.5rem 0;
      text-align: center;
      color: white;
      border-bottom: 1px solid white;
      text-transform: uppercase;
      cursor: pointer;
      letter-spacing: 2px;

      &:first-of-type {
        border-top: 1px solid white;
      }

      &:last-of-type {
        border: unset;
        border: 3px solid white;
        border-radius: 10px;
        margin-top: 1rem;
        font-weight: $font-semi-bold;
      }
    }

    &__lower {
      display: flex;
      flex-direction: column;
    }

    &__footer {
      text-align: center;
    }

    &__footer-item {
      margin-right: 3rem;

      &:last-of-type {
        margin-right: 0;
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

  <div class="mobile-nav-icon" on:click={handleMenuClick}>
    <img src="../assets/icon-hamburger.svg" alt="Mobile Menu" />
  </div>

  {#if $menuOpenState === true}
    <div class="mobile-nav">
      <div class="mobile-nav__upper">
        <div class="mobile-nav__heading">
          <img src="./assets/mobile-logo.svg" alt="Bookmark Logo" />
          <img
            on:click={handleMenuClick}
            class="mobile-nav__close"
            src="./assets/icon-close.svg"
            alt="Close Btn" />
        </div>
        <div class="mobile-nav__links">
          <a class="mobile-nav__link">Features</a>
          <a class="mobile-nav__link">Pricing</a>
          <a class="mobile-nav__link">Contact</a>
          <a class="mobile-nav__link">Login</a>
        </div>
      </div>
      <div class="mobile-nav__lower">
        <div class="mobile-nav__footer">
          <img
            class="mobile-nav__footer-item"
            src="./assets/icon-facebook.svg"
            alt="Facebook Logo" />
          <img
            class="mobile-nav__footer-item"
            src="./assets/icon-twitter.svg"
            alt="Twitter Logo" />
        </div>
      </div>

    </div>
  {/if}
</header>
