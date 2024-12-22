<script setup>
import BrowseDropdown from './BrowseDropdown.vue'
import NewsDropdown from './NewsDropdown.vue'
import FadeTransition from './FadeTransition.vue'
import { ref, computed } from 'vue'

const DropdownType = {
  BROWSE: 'BROWSE',
  NEWS: 'NEWS',
}

const openedDropdownType = ref('')
const browseDropdownOpened = computed(() => {
  return openedDropdownType.value === DropdownType.BROWSE
})

const newsDropdownOpened = computed(() => {
  return openedDropdownType.value === DropdownType.NEWS
})

const showOverlay = computed(() => {
  return Object.values(DropdownType).includes(openedDropdownType.value)
})

const onBrowseMenuClick = () => {
  if (openedDropdownType.value === DropdownType.BROWSE) {
    openedDropdownType.value = ''
  } else {
    openedDropdownType.value = DropdownType.BROWSE
  }
}

const onNewsMenuClick = () => {
  if (openedDropdownType.value === DropdownType.NEWS) {
    openedDropdownType.value = ''
  } else {
    openedDropdownType.value = DropdownType.NEWS
  }
}

const onOverlayClick = () => {
  openedDropdownType.value = ''
}
</script>

<template>
  <nav>
    <ul class="navbar">
      <li
        class="nav-item"
        :class="[browseDropdownOpened && 'bg-gray-900']"
        @click="onBrowseMenuClick"
      >
        <span>Browse</span>
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
          <path fill="currentColor" d="m12 15l5-5H7z" />
        </svg>
        <FadeTransition>
          <BrowseDropdown v-show="browseDropdownOpened" />
        </FadeTransition>
      </li>
      <li class="nav-item">Games</li>
      <li class="nav-item" :class="[newsDropdownOpened && 'bg-gray-900']" @click="onNewsMenuClick">
        <span>News</span>
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
          <path fill="currentColor" d="m12 15l5-5H7z" />
        </svg>
        <FadeTransition>
          <NewsDropdown v-show="newsDropdownOpened" />
        </FadeTransition>
      </li>
    </ul>
  </nav>
  <FadeTransition>
    <div class="overlay" v-show="showOverlay" @click="onOverlayClick"></div>
  </FadeTransition>
</template>

<style scoped>
.overlay {
  @apply fixed top-0 right-0 left-0 bottom-0 z-0 w-full h-full bg-gray-950/80;
}

.navbar {
  @apply bg-gray-800 flex relative z-30;
}

.nav-item {
  @apply px-5 py-4 font-main relative cursor-pointer text-gray-200
  flex items-center gap-1 select-none transition-colors hover:bg-gray-900;
}
</style>
