<script>
  import Seo from "../lib/components/SEO.svelte"
  import Section from "../lib/components/Section.svelte"
  import Nav from "./Nav.svelte"
</script>

<Seo />

<h1>Laura Goldthwaite</h1>
<Nav />

<Section id="about">About me</Section>
<Section theme="medium" id="social">Social Media</Section>
<Section id="mission">Mission</Section>
<Section theme="dark" id="portfolio">Portfolio</Section>
<Section id="contactme">Contact me</Section>

<style>
  h1 {
    font-size: var(--font-size-hero);
    font-family: var(--title-font);
  }
</style>
