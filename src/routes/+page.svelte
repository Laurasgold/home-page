<script>
  import Github from "$lib/assets/Github.svelte"
  import Instagram from "$lib/assets/Instagram.svelte"
  import Linkedin from "$lib/assets/Linkedin.svelte"
  import Seo from "../lib/components/SEO.svelte"
  import Section from "../lib/components/Section.svelte"
  import Nav from "./Nav.svelte"
  import aboutMeImg from "$lib/assets/images/laura.jpg"
  import missionImg from "$lib/assets/images/flower.jpg"

  let form
  let status = ""

  function onSubmit(event) {
    event.preventDefault()
    const data = new FormData(event.target)
    fetch(event.target.action, {
      method: form.method,
      body: data,
      headers: {
        Accept: "application/json",
      },
    })
      .then((response) => {
        if (response.ok) {
          status = "Thanks for your submission!"
          form.reset()
        } else {
          response.json().then((data) => {
            if (Object.hasOwn(data, "errors")) {
              status = data["errors"].map((error) => error["message"]).join(", ")
            } else {
              status = "Oops! There was a problem submitting your form"
            }
          })
        }
      })
      .catch((error) => {
        status = "Oops! There was a problem submitting your form"
      })
  }
</script>

<Seo />
<div class="hero wrapper">
  <h1 class="hero">Laura Goldthwaite</h1>
</div>
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
    <h3>Follow my social media</h3>
    <div class="social-links">
      <a href="https://www.instagram.com/laura.latest.study/"><Instagram /></a>
      <a href="https://www.linkedin.com/in/laura-goldthwaite-2129592b2/"><Linkedin /></a>
      <a href="https://github.com/Laurasgold"><Github /></a>
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
  <div class="portfolio">
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
  </div>
</Section>

<Section id="contact-me">
  <div class="contact-me">
    <h2 class="contact-me-title">Contact Me</h2>
    <p class="contact-me-description">I would love to hear from you.</p>
    <div class="contact-me-container">
      <div class="contact-me-card">
        <h3>Send a message</h3>
        <form on:submit={onSubmit} action="https://formspree.io/f/xvgpgedp" method="POST" bind:this={form}>
          <label for="">
            <span> Name: </span>
            <input name="name" />
          </label>
          <label for="">
            <span> Email: </span>
            <input type="email" name="email" />
          </label>
          <label for="">
            <span> Message: </span>
            <textarea rows="5" name="message" />
          </label>
          <button type="submit" class="submit-button">Submit Message</button>
        </form>
        {#if status}
          <p>{status}</p>
        {/if}
      </div>
    </div>
  </div>
</Section>

<style>
  h1 {
    font-size: var(--font-size-hero);
    font-family: var(--title-font);
  }
  h2 {
    font-size: var(--font-size-large);
  }
  h3 {
    font-size: var(--font-size-medium);
  }
  /************************************* 
Hero
**************************************/
  .wrapper {
    background-image: url(src/lib/assets/images/hero.png);
    /* background: pink; */
    background-size: cover;
    background-repeat: no-repeat;
    background-position: bottom;
    height: 959px;
    width: 100%;
  }

  .hero {
    justify-content: center;
    align-content: center;
    text-align: center;
    background-color: rgba(217, 217, 217, 0.5);
    padding-top: 30px;
  }

  @media screen and (max-width: 430px) {
    .wrapper {
      height: 325px;
      width: 100%;
    }
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
  .social h3 {
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
    padding-top: 4rem;
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
  /************************************* 
Contact Me section 
**************************************/
  .contact-me h3 {
    color: var(--dark-crayola);
    margin-right: 5rem;
  }

  .contact-me-title {
    display: flex;
    justify-content: center;
    padding-top: 140px;
    color: var(--dark-crayola);
  }

  .contact-me-description {
    display: flex;
    justify-content: center;
    padding-bottom: 120px;
    color: var(--blue-sand);
  }

  .contact-me-card {
    display: flex;
    /* makes it so that there is a column down with 1 item */
    flex-direction: column;
    /* grid-template-columns: 1fr; */
    gap: 3rem;
    background: var(--cadet);
    border-radius: var(--card-radius);
    padding: 85px 132px;
    margin: 0 auto;
    max-width: 75vw;
    width: 100%;
  }
  .contact-me-container {
    display: flex;
    justify-content: center;
  }
  label {
    width: 100%;
    display: flex;
    justify-content: flex-end;
    gap: 1rem;
  }

  form {
    display: grid;
    /* makes it so that there is a column down with 1 item */
    grid-template-columns: 1fr;
    gap: 3rem;
    justify-items: flex-end;
  }

  @media screen and (max-width: 820px) {
    .contact-me-card {
      padding: 8px;
      max-width: 100vw;
    }
    .contact-me h3 {
      text-align: center;
      margin-right: 0;
    }
    .submit-button {
      display: flex;
      justify-content: center;
    }
  }
</style>
