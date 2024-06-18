<script>
  import Github from "$lib/assets/Github.svelte"
  import Instagram from "$lib/assets/Instagram.svelte"
  import Linkedin from "$lib/assets/Linkedin.svelte"
  import Seo from "../lib/components/SEO.svelte"
  import Section from "../lib/components/Section.svelte"
  import Nav from "./Nav.svelte"
</script>

<Seo />

<h1>Laura Gold</h1>
<Nav />

<Section id="about">About me</Section>
<Section theme="medium" id="social">
  <div class="social">
    <h2>Follow my social media</h2>
    <div class="socialLinks">
      <Instagram />
      <Linkedin />
      <Github />
    </div>
  </div>
</Section>
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

  .social h2 {
    font-size: var(--font-size-medium);
    font-family: var(--title-font);
    text-align: center;
    padding-top: clamp(120px, 1.5vw, 330px);
  }
  /* need to work on padding top and bottom depending on when the other parts of the site ar added */
  .socialLinks {
    display: flex;
    justify-content: space-around;
    gap: 2rem;
    padding-top: 7%;
    padding-bottom: clamp(120px, 1vw, 330px);
    margin: 0 auto;
    max-width: 1028px;
  }

  @media screen and (max-width: 800px) {
    .portfolioContainer {
      flex-direction: column;
      justify-content: center;
    }
  }
</style>
