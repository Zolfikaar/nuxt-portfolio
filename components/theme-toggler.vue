<script setup lang="ts">
import { ref } from 'vue'

import sunIcon from './icons/sun.vue'
import MoonIcon from './icons/moon.vue'

const colorMode = useColorMode()

let theme = ref('')

function toggleTheme() {
  colorMode.preference = colorMode.preference === 'dark' ? 'light' : 'dark'
  theme.value = colorMode.preference
}

onMounted(() => {
  theme.value = colorMode.preference
})

</script>

<template>


  <button @click="toggleTheme">
    <div v-if="theme === 'light'">
      <MoonIcon />
    </div>
    <div v-else>
      <sunIcon />
    </div>
  </button>


</template>

<style scoped>
button {
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
</style>