<script>
  import Github from "$lib/assets/Github.svelte"
  import Instagram from "$lib/assets/Instagram.svelte"
  import Linkedin from "$lib/assets/Linkedin.svelte"
  import Seo from "../lib/components/SEO.svelte"
  import Section from "../lib/components/Section.svelte"
  import Nav from "./Nav.svelte"
  import aboutMeImg from "$lib/assets/images/laura.jpg"
  import missionImg from "$lib/assets/images/flower.jpg"
</script>

<Seo />

<h1>Laura Gold</h1>
<Nav />

<Section id="about">
  <div class="about">
    <div class="about-img-wrapper">
      <div class="image-background">
        <img src={aboutMeImg} alt="Laura" class="about-photo" />
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
<Section id="mission">
  <div class="mission">
    <div class="mission-text">
      <h2 class="mission-title">Mission</h2>
      <p class="mission-description">
        I bring a unique perspective and a deep commitment to innovation and continuous learning. My diverse background
        enables me to tackle challenges creatively and effectively, always striving for excellence in dynamic
        environments. I am dedicated to leveraging my skills and experiences to deliver cutting-edge solutions that make
        a positive impact. Whether it's through adapting to new technologies or providing insights gained from my global
        travels, I am committed to helping my clients navigate the complexities of the tech industry with confidence and
        success. Together, let's drive meaningful change and achieve outstanding results.
      </p>
    </div>
    <div class="mission-img-wrapper">
      <div class="image-background">
        <img src={missionImg} alt="bouquet of flowers" class="mission-photo" />
      </div>
    </div>
  </div>
</Section>

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
About Me & Mission section 
**************************************/
  .about,
  .mission {
    display: grid;
    align-items: center;
    gap: 3rem;
    padding: 1.5rem;
  }
  .about-title,
  .mission-title {
    color: var(--dark-crayola);
  }
  .about-description,
  .mission-description {
    line-height: 1.75;
  }
  .about-img-wrapper,
  .mission-img-wrapper {
    margin: auto;
  }

  .image-background {
    background-color: var(--silver);
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 30px;
  }

  @media screen and (min-width: 950px) {
    .about,
    .mission {
      /* display: flex;
      flex-direction: column;
      align-items: center; */
      grid-template-columns: repeat(2, 1fr);
    }
    .image-background {
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
Mission section 
**************************************/
  .mission {
    display: grid;
    align-items: center;
    gap: 3rem;
    padding: 1.5rem;
  }
  .mission-title {
    color: var(--dark-crayola);
  }
  .mission-description {
    line-height: 1.75;
  }
  .mission-img-wrapper {
    margin: auto;
  }

  .image-wrapper {
    background-color: var(--silver);
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 30px;
  }

  @media screen and (min-width: 950px) {
    .mission {
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
    padding-top: 7rem;
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
