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
    <div class="social-links">
      <Instagram />
      <Linkedin />
      <Github />
    </div>
  </div>
</Section>
<Section id="mission">Mission</Section>

<Section theme="dark" id="portfolio">
  <h2 class="portfolio-title">Portfolio</h2>
  <div class="portfolio-container">
    <div class="portfolio-card">
      <p>blah blah</p>
    </div>

    <div class="portfolio-card">
      <p>blah blah</p>
    </div>

    <div class="portfolio-card">
      <p>blah blah</p>
    </div>
  </div>
</Section>
<Section id="contact-me">Contact me</Section>

<style>
  h1 {
    font-size: var(--font-size-hero);
    font-family: var(--title-font);
  }

  .social h2 {
    font-size: var(--font-size-medium);
    font-family: var(--title-font);
    text-align: center;
    padding-top: clamp(120px, 1.5vw, 330px);
  }
  /* need to work on padding top and bottom depending on when the other parts of the site ar added */
  .social-links {
    display: flex;
    justify-content: space-around;
    gap: 2rem;
    padding-top: 3rem;
    padding-bottom: clamp(120px, 1vw, 330px);
    margin: 0 auto;
    max-width: 1028px;
  }

  :global(.social-links svg) {
    height: var(--font-size-medium);
    width: var(--font-size-medium);
  }

  .portfolio-card {
    background: var(--cadet);
    height: 600px;
    max-width: 400px;
    border-radius: var(--card-radius);
  }

  .portfolio-container {
    display: grid;
    grid-template-columns: repeat(3, minmax(200px, 420px));
    justify-content: space-around;
    margin: 0 auto;
    padding: 3rem 0;
  }

  .portfolio-title {
    display: flex;
    justify-content: center;
    font-size: var(--font-size-large);
    padding-top: 3rem;
  }

  @media screen and (max-width: 1306px) {
    .portfolio-container {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .portfolio-card {
      height: clamp(14.063rem, 20.613vw + 9.425rem, 26.25rem);
      width: clamp(18.75rem, 12.685vw + 15.896rem, 26.25rem);
      margin: 2rem auto;
    }
  }
</style>
