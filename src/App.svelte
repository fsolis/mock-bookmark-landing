<script>
  import FAQ from "./components/FAQ.svelte";
  import Features from "./components/Features.svelte";
  import Footer from "./components/Footer.svelte";
  import Hero from "./components/Hero.svelte";
  import PageHeader from "./components/PageHeader.svelte";
  import Download from "./components/Download.svelte";
</script>

<style type="text/scss">
  @import "./styles/styles";

  .bookmark-site {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    font-size: $font-size;
    font-family: Rubik, "Courier New", Courier, monospace;
    max-width: $desktop;
    margin: 1rem auto;
  }
</style>

<main class="bookmark-site">
  <PageHeader />
  <Hero />
  <Features />
  <Download />
  <FAQ />
</main>

<Footer />
