<script>
  export let title = "Oppenheimer Energy";
  export let description = "Oppenheimer Energy"
</script>

<svelte:head>
  <!-- Primary Meta Tags -->
  <title>
    {title}
  </title>
  <meta name="title" content={title} />
  <meta name="description" content={description} />

  <!-- Open Graph / Facebook -->
  <meta property="og:type" content="website" />
  <meta property="og:url" content="https://oppenheimer.energy/" />
  <meta property="og:title" content={title} />
  <meta property="og:description" content={description} />
  <meta property="og:image" content="https://oppenheimer.energy/meta-card.png" />

  <!-- Twitter -->
  <meta property="twitter:card" content="summary_large_image" />
  <meta property="twitter:url" content="https://oppenheimer.energy/" />
  <meta property="twitter:title" content={title} />
  <meta property="twitter:description" content={description} />
  <meta property="twitter:image" content="https://oppenheimer.energy/meta-card.png" />
</svelte:head>