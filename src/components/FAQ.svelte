<script>
  import { Collapse, CollapseItem } from "./Collapse";
</script>

<style type="text/scss">
  @import "../styles/styles";

  .faq {
    margin: 0 auto;

    &__content {
      display: flex;
      flex-direction: column;
    }

    &__heading {
      text-align: center;
      max-width: 650px;
      margin: 0 auto;
    }

    &__header {
      color: $drk-blue;
    }

    &__sub-header {
      color: $grey-blue;
    }

    &__info-btn {
      margin: 3rem auto;
    }
  }

  :global(.faq-collapse.collapse) {
    max-width: 650px;
    overflow: hidden;
    margin: 1rem;

    :global(.collapse-item) {
      color: $drk-blue;
      border-top: 1px solid $light-grey;
      padding: 0.5rem;

      :global(.collapse-item__panel > p) {
        color: $grey-blue;
      }

      &:last-of-type {
        border-bottom: 1px solid $light-grey;
      }
    }
  }
</style>

<section class="faq">
  <div class="faq__heading">
    <h1 class="faq__header">Frequently Asked Questions</h1>
    <h3 class="faq__sub-header">
      Here are some of our FAQs. If you have any questions you'd like answered
      please feel free to email us.
    </h3>
  </div>
  <div class="faq__content">
    <Collapse class="faq-collapse">
      <CollapseItem title="What is Bookmark?">
        <p>What is Bookmark?</p>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla
          tristique et lectus a lobortis. Nullam eget accumsan purus. Aliquam
          tincidunt mauris et urna semper bibendum. Aenean et ante sagittis
          metus varius fermentum id at tortor. Morbi lobortis leo sit amet
          sagittis porttitor. Vivamus sit amet convallis ligula, eu vulputate
          massa. Morbi tincidunt est eget efficitur maximus. Sed sit amet
          sodales velit, a condimentum massa. In aliquam orci tortor, id
          consequat libero gravida non.
        </p>
      </CollapseItem>
      <CollapseItem title="How can I request a new browser?">
        <p>How can I request a new browser?</p>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla
          tristique et lectus a lobortis. Nullam eget accumsan purus. Aliquam
          tincidunt mauris et urna semper bibendum. Aenean et ante sagittis
          metus varius fermentum id at tortor. Morbi lobortis leo sit amet
          sagittis porttitor. Vivamus sit amet convallis ligula, eu vulputate
          massa. Morbi tincidunt est eget efficitur maximus. Sed sit amet
          sodales velit, a condimentum massa. In aliquam orci tortor, id
          consequat libero gravida non.
        </p>
      </CollapseItem>
      <CollapseItem title="Is there a mobile app?">
        <p>Is there a mobile app?</p>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla
          tristique et lectus a lobortis. Nullam eget accumsan purus. Aliquam
          tincidunt mauris et urna semper bibendum. Aenean et ante sagittis
          metus varius fermentum id at tortor. Morbi lobortis leo sit amet
          sagittis porttitor. Vivamus sit amet convallis ligula, eu vulputate
          massa. Morbi tincidunt est eget efficitur maximus. Sed sit amet
          sodales velit, a condimentum massa. In aliquam orci tortor, id
          consequat libero gravida non.
        </p>
      </CollapseItem>
      <CollapseItem title="What about other Chromium browsers?">
        <p>What about other Chromium browsers?</p>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nulla
          tristique et lectus a lobortis. Nullam eget accumsan purus. Aliquam
          tincidunt mauris et urna semper bibendum. Aenean et ante sagittis
          metus varius fermentum id at tortor. Morbi lobortis leo sit amet
          sagittis porttitor. Vivamus sit amet convallis ligula, eu vulputate
          massa. Morbi tincidunt est eget efficitur maximus. Sed sit amet
          sodales velit, a condimentum massa. In aliquam orci tortor, id
          consequat libero gravida non.
        </p>
      </CollapseItem>
    </Collapse>
    <button class="faq__info-btn btn btn--blue">More Info</button>
  </div>
</section>
