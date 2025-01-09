<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';

const activeLink = ref('/');
const router = useRouter();

router.afterEach((to) => {
  activeLink.value = to.path;
});

const setActiveLink = (path) => {
  activeLink.value = path;
};
</script>

<template>
  <nav class="font-mono">
    <ul class="flex space-x-4">
      <li>
        <NuxtLink to="/" class="link" :class="{ active: activeLink === '/' }" @click="setActiveLink('/')">
          Home
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/about" class="link" :class="{ active: activeLink === '/about' }"
          @click="setActiveLink('/about')">
          About
        </NuxtLink>
      </li>
      <li>
        <NuxtLink to="/projects" class="link" :class="{ active: activeLink === '/projects' }"
          @click="setActiveLink('/projects')">
          Projects
        </NuxtLink>
      </li>
    </ul>
  </nav>
</template>

<style scoped>
.link {
  @apply p-1 hover:bg-gray-200;
}

.active {
  @apply bg-gray-200;
}
</style>