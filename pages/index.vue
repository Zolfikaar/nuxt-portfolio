<script setup lang="ts">
const route = useRoute();

definePageMeta({
  // layout: 'x',
})

</script>

<template>
  <div>
    <h1>Home Page</h1>
    <p>Current route: {{ route.name }}</p>

  </div>
</template>