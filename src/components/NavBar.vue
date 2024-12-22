<script setup>
import BrowseDropdown from './BrowseDropdown.vue'
import { ref } from 'vue'

const browseDropdownOpened = ref(false)

const onClickHandler = () => {
  browseDropdownOpened.value = !browseDropdownOpened.value
}
</script>

<template>
  <ul class="navbar">
    <li class="nav-item" :class="[browseDropdownOpened && 'bg-gray-900']" @click="onClickHandler">
      <span>Browse</span>
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
        <path fill="currentColor" d="m12 15l5-5H7z" />
      </svg>
    </li>
    <BrowseDropdown v-show="browseDropdownOpened" />
    <li class="nav-item">Games</li>
    <li class="nav-item">
      <span>News</span>
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
        <path fill="currentColor" d="m12 15l5-5H7z" />
      </svg>
    </li>
  </ul>
  <div class="overlay" v-show="browseDropdownOpened" @click="onClickHandler"></div>
</template>

<style scoped>
.overlay {
  @apply fixed top-0 right-0 left-0 bottom-0 z-0 w-full h-full bg-gray-950/80;
}

.navbar {
  @apply bg-gray-800 flex relative z-30;
}

.nav-item {
  @apply px-5 py-4 font-main cursor-pointer text-gray-200
  flex items-center gap-1 select-none transition-colors hover:bg-gray-900;
}
</style>
