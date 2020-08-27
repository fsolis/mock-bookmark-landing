<script>
  import { writable } from "svelte/store";
  let inputRef;
  const hasError = writable(false);

  const testEmail = (email) => {
    const emailReg = new RegExp(
      /(?:[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?|\[(?:(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?)\.){3}(?:25[0-5]|2[0-4][0-9]|[01]?[0-9][0-9]?|[a-z0-9-]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])/
    );
    return emailReg.test(email);
  };

  const handleClick = () => {
    const { value } = inputRef;
    if (value && testEmail(value)) {
      return hasError.set(false);
    }
    return hasError.set(true);
  };
</script>

<style type="text/scss">
  @import "../styles/styles";

  .contact-input {
    display: flex;
    flex-direction: column;
    justify-content: center;

    @include medium {
      flex-direction: row;
    }

    &__btn {
      background-color: $primary-red;
      box-shadow: none;
      color: white;
      height: 50px;
      line-height: 1;
      white-space: nowrap;

      &:active,
      &:focus {
        border: 1px solid $primary-red;
        background-color: white;
        color: $primary-red;
      }
    }

    &__field {
      border-radius: 5px;
      border: none;
      margin: 0 auto 1rem auto;
      padding: 0 16px;
      height: 50px;
      width: calc(100% - #{32px});
      outline: none;

      @include medium {
        margin: 0;
        margin-right: 1rem;
        width: 285px;
      }

      &--error {
        border: 2px solid $primary-red;
      }
    }

    &__field-container {
      position: relative;
    }

    &__field-error {
      position: absolute;
      height: 20px;
      border-radius: 0 0 5px 5px;
      bottom: -40px;
      padding-top: 10px;
      text-align: left;
      padding-left: 5px;
      background-color: $primary-red;
      width: 316px;
      font-size: 12px;
    }
  }
</style>

<div class="contact-input">
  <div class="contact-input__field-container">
    <input
      bind:this={inputRef}
      class:contact-input__field--error={$hasError === true}
      class="contact-input__field"
      placeholder="Enter your email address"
      maxlength="70" />
    {#if $hasError === true}
      <p class="contact-input__field-error">Whoops. Make sure it's an email</p>
    {/if}
  </div>

  <button class="contact-input__btn btn is-red" on:click={handleClick}>
    Contact Us
  </button>
</div>
