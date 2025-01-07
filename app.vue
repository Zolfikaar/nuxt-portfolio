<script setup lang="ts">
const layout = 'default';
useHead({
  title: 'My App',
  meta: [
    { name: 'description', content: 'My amazing site.' }
  ],
  bodyAttrs: {
    class: 'test'
  },
  script: [ { innerHTML: 'console.log(\'Hello world\')' } ]
})
</script>

<template>
  <NuxtLayout :name="layout">

    
    <NuxtPage />

  </NuxtLayout>
</template>
