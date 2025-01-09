<script setup>

const { error, pending, data } = await useFetch('https://api.github.com/users/Zolfikaar/repos')

console.log(data)
</script>

<template>
  <section v-if="pending">Loading...</section>
  <section v-else-if="error">Something went wrong... Try again</section>
  <section v-else>
    <ul class="grid grid-cols-3 gap-4" v-if="data">
      <li v-for="repo in data" :key="repo.id"
        class="border border-gray-100 p-4 rounded-sm shadow-sm hover:shadow-md hover:cursor-pointer transition duration-300 min-width-48">
        <a :href="repo.html_url">{{ repo.name }}</a>
      </li>
    </ul>

    <p v-else>No data</p>
  </section>
</template>