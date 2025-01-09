<template>
  <div>
    <h1>About Page</h1>
  </div>
</template>

<script setup lang="ts">
definePageMeta({
  // layout: 'x'
})

useSeoMeta({
  title: 'My Amazing Site',
  ogTitle: 'My Amazing Site',
  description: 'This is my amazing site, let me tell you all about it.',
  ogDescription: 'This is my amazing site, let me tell you all about it.',
  ogImage: 'https://example.com/image.png',
  twitterCard: 'summary_large_image',
})
</script>

<style scoped>
h1 {
  color: #333;
}
</style>