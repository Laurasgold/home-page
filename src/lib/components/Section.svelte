<script>
  export let theme = "normal"
  export let id

  const themeMap = {
    normal: {
      heading: "var(--dark-sage)",
      text: "var(--blue-sand)",
      background: "var(--warm-sand)",
    },
    medium: {
      heading: "var(--dark-crayola)",
      text: "var(--dark-crayola)",
      background: "var(--crayola)",
    },
    dark: {
      heading: "var(--warm-sand)",
      text: "var(--warm-sand)",
      background: "var(--dark-crayola)",
    },
  }
</script>

<section style="background: {themeMap[theme].background}; color: {themeMap[theme].text};" {id}>
  <!-- magic portal whatever you write in the Section tag is places in the portal tag -->
  <slot></slot>
</section>

<style>
  section {
    padding-left: 1rem;
    padding-right: 1rem;
  }
</style>
