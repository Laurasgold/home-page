<script>
  import Seo from "../lib/components/SEO.svelte"
  import Section from "../lib/components/Section.svelte"
</script>

<Seo />

<h1>Laura Goldthwaite</h1>
<Section>About me</Section>
<Section theme="medium">Social Media</Section>
<Section>Mission</Section>
<Section theme="dark">Portfolio</Section>
<Section>Contact me</Section>

<style>
  h1 {
    font-size: var(--font-size-hero);
    font-family: var(--title-font);
  }
</style>
