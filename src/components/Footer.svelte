<script>
  import Contact from "./Contact.svelte";
</script>

<style type="text/scss">
  @import "../styles/styles";

  .footer {
    background-color: $primary-blue;
    color: white;
    display: flex;
    flex-direction: column;
    margin-top: 3rem;
    text-align: center;

    &__sub-heading {
      text-transform: uppercase;
      letter-spacing: 4px;
      margin-top: 2.5rem;
      margin-bottom: 0;
    }

    &__heading {
      margin-bottom: 2.5rem;
    }

    &__contact {
      margin: auto;
      max-width: 400px;
      padding: 16px;

      @include medium {
        padding: 0;
      }
    }

    &__nav {
      background-color: $drk-blue;
      display: flex;
      flex-direction: column;
      padding: 10px;
      margin-top: 2rem;

      @include medium {
        flex-direction: row;
        justify-content: space-between;
      }
    }

    &__nav-icons {
      display: flex;
      align-items: center;
      justify-content: center;
      margin: 1rem 0;

      @include medium {
        justify-content: flex-start;
        margin: 0;
      }

      @include large {
        margin-right: 4rem;
      }
    }

    &__nav-links {
      display: flex;
      flex-direction: column;

      @include medium {
        flex-direction: row;
        align-items: center;
      }
    }

    &__nav-icon {
      margin: 0 1rem;
      cursor: pointer;

      &:hover {
        color: $primary-red;
      }
    }

    &__nav-link {
      margin: 1rem;
      font-size: 15px;
      text-transform: uppercase;
      letter-spacing: 1px;
      cursor: pointer;

      @include medium {
        margin: 1.5rem 1rem;
      }

      @include large {
        margin: 1.5rem;
      }

      &:hover {
        color: $primary-red;
      }
    }

    &__logo {
      width: auto;
      height: 25px;
      margin: 1rem auto;

      @include medium {
        height: 35px;
        margin: 0 2rem;
      }

      @include large {
        margin: 0 2rem 0 4rem;
      }
    }
  }
</style>

<footer class="footer">
  <div class="footer__contact">
    <h4 class="footer__sub-heading">35,000+ Already Joined</h4>
    <h1 class="footer__heading">Stay up-to-date with what we're doing</h1>
    <Contact />
  </div>
  <div class="footer__nav">
    <div class="footer__nav-links">
      <img
        class="footer__logo"
        src="../assets/logo-bookmark-white.svg"
        alt="Bookmark Logo" />
      <p class="footer__nav-link">Features</p>
      <p class="footer__nav-link">Pricing</p>
      <p class="footer__nav-link">Contact</p>
    </div>
    <div class="footer__nav-icons">
      <img
        class="footer__nav-icon"
        src="../assets/icon-facebook.svg"
        alt="Facebook Logo" />
      <img
        class="footer__nav-icon"
        src="../assets/icon-twitter.svg"
        alt="Twitter Logo" />
    </div>
  </div>
</footer>
