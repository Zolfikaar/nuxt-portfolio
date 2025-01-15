<script setup>

const { error, pending, data } = await useFetch('https://api.github.com/users/Zolfikaar/repos')
let createionDate = data.value[0].created_at

const repos = computed(() =>
  data.value.filter(repo => repo.description)
    .sort((a, b) => b.created_at - a.created_at)

)
</script>

<template>
  <section v-if="pending">Loading...</section>
  <section v-else-if="error">Something went wrong... Try again</section>
  <section v-else>
    <ul class="grid grid-cols-1 gap-4" v-if="data">
      <NuxtLink :to="`/projects/${repo.name}`" :repo="repo" v-for="repo in repos" :key="repo.id"
        class="border border-gray-100 p-4 rounded-sm shadow-sm hover:shadow-md hover:cursor-pointer transition duration-300 drop-shadow-md hover:drop-shadow-[0_35px_35px_rgba(0,0,0,0.25)] ease-in-out">
        <li>

          <!-- <a :href="repo.html_url" target="_blank">
            <div class="font-semibold">{{ repo.name }}</div>
          </a> -->
          <div class="font-semibold flex justify-between items-center">
            <div>{{ repo.name }}</div>
            <div class="text-sm text-gray-500">{{ repo.created_at.split("T")[0] }}</div>
          </div>

        </li>

        <p class="text-sm text-gray-500 mt-5">{{ repo.description }}</p>
      </NuxtLink>

    </ul>

    <p v-else>No data</p>
  </section>
</template>