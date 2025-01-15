<script setup>
const route = useRoute()

const { error, pending, data } = await useFetch('https://api.github.com/users/Zolfikaar/repos')

const repo = ref(data.value.filter(repo => repo.name == route.params.slug)[0])


// console.log(repo.value)

</script>


<template>
  <h1>project details</h1>
  <div v-if="pending">Loading...</div>
  <div v-else-if="error">Something went wrong... Try again</div>
  <div v-else>
    <div>Repo name: {{ repo.name }}</div>
    <p>Repo description: {{ repo.description }}</p>
    <div>Repo created at: {{ repo.created_at.split("T")[0] }}</div>
    <div>Repo updated at: {{ repo.updated_at.split("T")[0] }}</div>
    <a :href="repo.deployments_url">Live Preview</a>
  </div>

</template>