<script>
  import ImageHero from "./ImageHero.svelte";
  import { Tabs, TabList, TabPanel, Tab } from "./Tabs";
</script>

<style type="text/scss">
  @import "../styles/styles";

  .features {
    display: flex;
    flex-direction: column;
    text-align: center;
    color: $drk-blue;

    &__heading {
      margin-bottom: 2rem;
    }

    &__sub-heading {
      color: $grey-blue;
      max-width: 80%;
      margin: 0 auto 2.25rem auto;
      font-size: 1.25rem;
      line-height: 2rem;

      @include large {
        max-width: 50%;
      }
    }

    &__searching {
      .tab-panel__img {
        width: 550px;
      }
    }
  }

  .features :global(.tab-panel) {
    padding: 1rem;
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    margin: 3rem 0;

    @include medium {
      flex-direction: row;
    }
  }

  .tab-panel {
    display: flex;

    &__right {
      flex: 1;
      text-align: center;

      @include medium {
        margin: auto 0 auto 0;
        flex: 1 1 35%;
        text-align: start;
        padding-left: 1rem;
      }
    }

    &__description {
      font-size: 1.25rem;
      color: $grey-blue;
      max-width: 80%;
      margin: 2rem auto;

      @include medium {
        max-width: 100%;
        margin: 2rem 0;
      }
    }

    &__img {
      width: 80%;
    }
  }

  :global(.img-hero > .feature-img-hero) {
    position: relative;
    height: 180px;
    width: auto;
    margin: auto;
    z-index: 2;

    @include small {
      height: 240px;
    }

    @include small-medium {
      height: 300px;
    }

    @include medium {
      height: 100%;
    }
  }
</style>

<section class="features">
  <h1 class="features__heading">Features</h1>
  <p class="features__sub-heading">
    Our aim is to make it quick and easy for you to access your favorite
    websites. Your bookmarks sync between your devcies so you can access them on
    the go.
  </p>

  <Tabs>
    <TabList>
      <Tab>Simple Bookmarking</Tab>
      <Tab>Speedy Searching</Tab>
      <Tab>Easy Sharing</Tab>
    </TabList>
    <TabPanel>
      <ImageHero directionRight={false}>
        <img
          class="feature-img-hero"
          src="../assets/illustration-features-tab-1.svg"
          alt="bookmark in one click" />
      </ImageHero>
      <div class="tab-panel__right">
        <h1>Bookmark in one click</h1>
        <p class="tab-panel__description">
          Organize your bookmarks however you like. Our simple drag-and-drop
          interface gives you complete control over how you manage your favorite
          sites.
        </p>
        <button class="btn btn--blue">More Info</button>
      </div>
    </TabPanel>
    <TabPanel>
      <ImageHero directionRight={false}>
        <img
          src="../assets/illustration-features-tab-2.svg"
          alt="Intelligent search" />
      </ImageHero>
      <div class="tab-panel__right">
        <h1>Intelligent Search</h1>
        <p class="tab-panel__description">
          Our powerful search feature will help you find saved sites in no time
          at all. No need to thawl through all of your bookmarks.
        </p>
        <button class="btn btn--blue">More Info</button>
      </div>
    </TabPanel>
    <TabPanel>
      <ImageHero directionRight={false}>
        <img
          src="../assets/illustration-features-tab-3.svg"
          alt="Intelligent search" />
      </ImageHero>
      <div class="tab-panel__right">
        <h1>Share your bookmarks</h1>
        <p class="tab-panel__description">
          Easily share your bookmarks and collections with others. Create a
          shareable link that you can send at the click of a button.
        </p>
        <button class="btn btn--blue">More Info</button>
      </div>
    </TabPanel>
  </Tabs>
</section>
