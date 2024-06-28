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

<Section id="about">
  <div class="about">
    <div style="margin:auto;">
      <div class="image-wrapper">
        <img src="/src/lib/assets/images/20230914_192008.jpg" alt="Laura" srcset="" class="about-photo" />
      </div>
    </div>
    <div class="about-text">
      <h2 class="about-title">About Me</h2>
      <p class="about-description">
        I'm a former nurse turned tech enthusiast with a passion for innovation and continuous learning. My diverse
        background enables me to approach challenges with a unique perspective. I thrive in dynamic environments,
        quickly adapting to new situations and technologies. In my free time, I enjoy traveling, which fuels my
        curiosity and broadens my understanding of the world. I'm committed to leveraging my skills to make a positive
        impact in the tech industry.
      </p>
    </div>
  </div>
</Section>
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
  h2 {
    font-size: var(--font-size-medium);
  }

  /************************************* 
About Me section 
**************************************/
  .about {
    display: grid;
    align-items: center;
    gap: 3rem;
    padding: 1.5rem;
  }
  .about-title {
    color: var(--dark-crayola);
  }
  .about-description {
    line-height: 1.75;
    text-align: left;
  }

  .image-wrapper {
    /* border: 51px solid var(--silver); */
    background-color: var(--silver);
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 30px;
  }

  @media screen and (min-width: 950px) {
    .about {
      /* display: flex;
      flex-direction: column;
      align-items: center; */
      grid-template-columns: repeat(2, 1fr);
    }
    .image-wrapper {
      transform: translateY(88px);
      padding: 45px;
    }
  }
  /************************************* 
Social Media section 
**************************************/
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

  /************************************* 
Portfolio section 
**************************************/

  .portfolio-card {
    background: var(--cadet);
    height: 600px;
    /* max-width: 400px; */
    border-radius: var(--card-radius);
  }

  .portfolio-container {
    display: grid;
    grid-template-columns: repeat(3, 1fr);

    margin: 0 auto;
    padding: 3rem 0;
    gap: 2rem;
  }

  .portfolio-title {
    display: flex;
    justify-content: center;
    padding-top: 3rem;
  }

  @media screen and (max-width: 800px) {
    .portfolio-container {
      /* display: flex;
      flex-direction: column;
      align-items: center; */
      grid-template-columns: 1fr;
    }
    .portfolio-card {
      /* height: clamp(14.063rem, 20.613vw + 9.425rem, 26.25rem);
      width: clamp(18.75rem, 12.685vw + 15.896rem, 26.25rem); */
      max-width: none;
    }
  }
</style>
