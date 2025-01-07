<script setup lang="ts">
const route = useRoute();

definePageMeta({
  // layout: 'x',
})

useSeoMeta({
  ogTitle: 'Tholfikar Moh. Portfolio',
  ogDescription: 'My Portfolio',
  ogImage: '[og:image]',
  ogUrl: '[og:url]',
  twitterTitle: 'Tholfikar Moh. Portfolio',
  twitterDescription: 'My Portfolio',
  twitterImage: '[twitter:image]',
  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'en'
  },
  link: [
    {
      rel: 'icon',
      type: 'image/png',
      href: '/favicon.png'
    }
  ]
})

</script>

<template>
  <div>
    <h1>Home Page</h1>

  </div>
</template>

