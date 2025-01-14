<script setup>

const { error, pending, data } = await useFetch('https://api.github.com/users/Zolfikaar/repos')
let createionDate = data.value[0].created_at
console.log(createionDate.trim(0, 10))

const repos = computed(() =>
  data.value.filter(repo => repo.description)
    .sort((a, b) => b.created_at - a.created_at)
  // .trim(repo => repo.created_at > new Date().toISOString())
)
</script>

<template>
  <section v-if="pending">Loading...</section>
  <section v-else-if="error">Something went wrong... Try again</section>
  <section v-else>
    <ul class="grid grid-cols-1 gap-4" v-if="data">
      <li v-for="repo in repos" :key="repo.id"
        class="border border-gray-100 p-4 rounded-sm shadow-sm hover:shadow-md hover:cursor-pointer transition duration-300 ">
        <NuxtLink :to="`/projects/${repo.name}`" :repo="repo">
          <!-- <a :href="repo.html_url" target="_blank">
            <div class="font-semibold">{{ repo.name }}</div>
          </a> -->
          <div class="font-semibold flex justify-between items-center">
            <div>{{ repo.name }}</div>
            <div class="text-sm text-gray-500">{{ repo.created_at }}</div>
          </div>
        </NuxtLink>

        <p class="text-sm text-gray-500 mt-5">{{ repo.description }}</p>
      </li>
    </ul>

    <p v-else>No data</p>
  </section>
</template>