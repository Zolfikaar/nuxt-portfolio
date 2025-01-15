<template>
  <div class="container mx-auto max-w-2xl">

    <header class="flex justify-between items-center mt-5 mb-7">
      <div>
        <NuxtLink to="/" class="text-xl p-1 font-semibold ">
          Tholfikar Mohammed
        </NuxtLink>
      </div>

      <Menu />

      <ThemeToggler />
    </header>

    <main class="p-2">
      <slot />
    </main>

  </div>
</template>

<script setup >
useHead({
    titleTemplate: '%s - Tholfikar Mohammed',
    // meta: [
    //   { name: 'description', content: 'My Portfolio' }
    // ],
    // bodyAttrs: {
    //   class: 'bg-gray-100'
    // },
    // script: [ { innerHTML: 'console.log(\'Hello world\')' } ],

    link: [
      {
        rel: 'preconnect',
        href: 'https://fonts.googleapis.com'
      },
      {
        rel: 'stylesheet',
        href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap',
        crossorigin: ''
      }
    ],
  })

// export default {
//   name: 'default',
  
// }
</script>

<style>
body{
  font-family: 'Roboto';
}

body {
  @apply bg-white dark:bg-gray-900 text-gray-700 dark:text-gray-300;
}

</style>