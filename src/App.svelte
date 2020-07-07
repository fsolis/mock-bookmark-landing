<script>
  import Footer from "./components/Footer.svelte";
  import PageHeader from "./components/PageHeader.svelte";
</script>

<style type="text/scss">
  @import "./styles/styles";

  .bookmark {
    display: flex;
    flex-direction: column;
    flex-grow: 1;
    font-size: $font-size;
    font-family: Rubik, "Courier New", Courier, monospace;
  }
</style>

<main class="bookmark">
  <PageHeader />
  <Footer />
</main>
