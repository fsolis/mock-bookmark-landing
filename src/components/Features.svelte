<script>
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
      max-width: 40%;
      margin: 0 auto 2.25rem auto;
      font-size: 1.25rem;
      line-height: 2rem;
    }

    &__searching {
      .tab-panel__img {
        width: 550px;
      }

      &.background-decorator--left:after {
        bottom: -30px;
      }
    }
  }

  :global(.tab-panel) {
    padding: 1rem;
    display: flex;
    flex-direction: row;
    flex-grow: 1;
    margin: 3rem 0;
  }

  .tab-panel {
    &__left {
      width: 65%;
    }

    &__right {
      width: 35%;
      margin: auto 0 auto 0;
      text-align: start;
    }

    &__description {
      font-size: 1.25rem;
      color: $grey-blue;
      max-width: 100%;
      margin: 2rem 0;
    }

    &__img {
      width: 650px;
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
      <div
        class="features__bookmarking tab-panel__left background-decorator--left">
        <img
          class="tab-panel__img"
          src="../assets/illustration-features-tab-1.svg"
          alt="bookmark in one click" />
      </div>
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
      <div
        class="features__searching tab-panel__left background-decorator--left">
        <img
          class="tab-panel__img"
          src="../assets/illustration-features-tab-2.svg"
          alt="Intelligent search" />
      </div>
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
      <div
        class="features__searching tab-panel__left background-decorator--left">
        <img
          class="tab-panel__img"
          src="../assets/illustration-features-tab-3.svg"
          alt="Intelligent search" />
      </div>
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
