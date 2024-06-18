<script>
  import Seo from "../lib/components/SEO.svelte"
  import Section from "../lib/components/Section.svelte"
  import Nav from "./Nav.svelte"
</script>

<Seo />

<h1>Laura Gold</h1>
<Nav />

<Section id="about">About me</Section>
<Section theme="medium" id="social">Social Media</Section>
<Section id="mission">Mission</Section>

<Section theme="dark" id="portfolio">
  <h2 class="portfolio">Portfolio</h2>
  <section class="portfolioContainer">
    <div class="portfolioBackground">
      <div class="sectionDescription">blah blah</div>
    </div>

    <div class="portfolioBackground">
      <div class="sectionDescription">blah blah</div>
    </div>

    <div class="portfolioBackground">
      <div class="sectionDescription">blah blah</div>
    </div>
  </section>
</Section>
<Section id="contactme">Contact me</Section>

<style>
  h1 {
    font-size: var(--font-size-hero);
    font-family: var(--title-font);
  }
  .portfolioBackground {
    background: var(--cadet);
    height: 600px;
    width: 420px;
    margin: 25px;
    border-radius: 5%;
  }

  .portfolioContainer {
    display: flex;
    justify-content: space-evenly;
    padding-bottom: 50px;
    margin: 1px;
  }
  .portfolio {
    display: flex;
    justify-content: center;
    padding: 236px;
    font-family: var(--title-font);
    font-size: var(--font-size-large);
    font-weight: 400;
  }

  .sectionDescription {
    display: flex;
    justify-content: center;
    padding-top: 8px;
  }

  @media screen and (max-width: 800px) {
    .portfolioContainer {
      flex-direction: column;
      justify-content: center;
    }
  }
</style>
