<script>
  const siteMetadata = {
    title: `Laura Goldthwaite`,
    description: `Web Developer Portfolio Building Websites. Let's Collaborate!`,
    author: `@lauras_gold`,
    siteUrl: "",
  }

  const { title, description, author } = siteMetadata
</script>

<svelte:head>
  <title>{title}</title>
  <meta name="description" content={description} />
  <meta property="og:title" content={title} />
  <meta property="og:description" content={description} />
  <meta property="og:type" content="website" />
  <meta name="twitter:card" content="summary" />
  <meta name="twitter:creator" content={author} />
  <meta name="twitter:title" content={title} />
  <meta name="twitter:description" content={description} />
</svelte:head>
