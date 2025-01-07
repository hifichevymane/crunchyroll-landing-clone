<script setup>
import BrowseDropdown from './BrowseDropdown.vue'
import NewsDropdown from './NewsDropdown.vue'
import FadeTransition from './FadeTransition.vue'
import AccountDropdown from './AccountDropdown.vue'
import PremiumTooltip from './PremiumTooltip.vue'

import { ref, computed } from 'vue'

const DropdownType = {
  CLOSED: 0,
  BROWSE: 1,
  NEWS: 2,
  ACCOUNT: 3,
}

const premiumTooltipOpened = ref(false)
const openedDropdownType = ref(DropdownType.CLOSED)
const browseDropdownOpened = computed(() => {
  return openedDropdownType.value === DropdownType.BROWSE
})

const newsDropdownOpened = computed(() => {
  return openedDropdownType.value === DropdownType.NEWS
})

const accountDropdownOpened = computed(() => {
  return openedDropdownType.value === DropdownType.ACCOUNT
})

const showOverlay = computed(() => {
  return openedDropdownType.value !== DropdownType.CLOSED
})

const onBrowseMenuClick = () => {
  if (openedDropdownType.value === DropdownType.BROWSE) {
    openedDropdownType.value = DropdownType.CLOSED
  } else {
    openedDropdownType.value = DropdownType.BROWSE
  }
}

const onNewsMenuClick = () => {
  if (openedDropdownType.value === DropdownType.NEWS) {
    openedDropdownType.value = DropdownType.CLOSED
  } else {
    openedDropdownType.value = DropdownType.NEWS
  }
}

const onAccountMenuClick = () => {
  if (openedDropdownType.value === DropdownType.ACCOUNT) {
    openedDropdownType.value = DropdownType.CLOSED
  } else {
    openedDropdownType.value = DropdownType.ACCOUNT
  }
}

const onOverlayClick = () => {
  openedDropdownType.value = DropdownType.CLOSED
}

const onTrialPremiumMouseOver = () => {
  premiumTooltipOpened.value = true
}
const onTrialPremiumMouseOut = () => {
  premiumTooltipOpened.value = false
}
</script>

<template>
  <nav>
    <ul class="navbar">
      <div class="nav-menu">
        <li class="nav-item logo">
          <img src="/src/assets/crunchyroll.svg" alt="Crunchyroll logo" />
        </li>
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
        <li
          class="nav-item"
          :class="[newsDropdownOpened && 'bg-gray-900']"
          @click="onNewsMenuClick"
        >
          <span>News</span>
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path fill="currentColor" d="m12 15l5-5H7z" />
          </svg>
          <FadeTransition>
            <NewsDropdown v-show="newsDropdownOpened" />
          </FadeTransition>
        </li>
      </div>
      <div class="nav-actions">
        <li
          class="nav-item premium-link"
          @mouseover="onTrialPremiumMouseOver"
          @mouseout="onTrialPremiumMouseOut"
        >
          <svg
            class="premium-logo"
            xmlns="http://www.w3.org/2000/svg"
            width="14"
            height="14"
            viewBox="0 0 14 14"
          >
            <path
              fill="currentColor"
              fill-rule="evenodd"
              d="M7.41 1.713a.5.5 0 0 0-.82 0L3.432 6.225L.854 3.646A.5.5 0 0 0 0 4v6.5a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V4a.5.5 0 0 0-.854-.354l-2.578 2.579z"
              clip-rule="evenodd"
            />
          </svg>
          <div>
            <span class="try-free-text">TRY FREE</span>
            <span class="premium-text">PREMIUM</span>
          </div>
          <FadeTransition>
            <PremiumTooltip v-show="premiumTooltipOpened" />
          </FadeTransition>
        </li>
        <li class="nav-item">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              fill="currentColor"
              d="m19.6 21l-6.3-6.3q-.75.6-1.725.95T9.5 16q-2.725 0-4.612-1.888T3 9.5t1.888-4.612T9.5 3t4.613 1.888T16 9.5q0 1.1-.35 2.075T14.7 13.3l6.3 6.3zM9.5 14q1.875 0 3.188-1.312T14 9.5t-1.312-3.187T9.5 5T6.313 6.313T5 9.5t1.313 3.188T9.5 14"
            />
          </svg>
        </li>
        <li class="nav-item">
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path fill="currentColor" d="M5 21V3h14v18l-7-3zm2-3.05l5-2.15l5 2.15V5H7zM7 5h10z" />
          </svg>
        </li>
        <li
          class="nav-item"
          :class="[accountDropdownOpened && 'bg-gray-900']"
          @click="onAccountMenuClick"
        >
          <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
            <path
              fill="currentColor"
              d="M12 4a4 4 0 0 1 4 4a4 4 0 0 1-4 4a4 4 0 0 1-4-4a4 4 0 0 1 4-4m0 2a2 2 0 0 0-2 2a2 2 0 0 0 2 2a2 2 0 0 0 2-2a2 2 0 0 0-2-2m0 7c2.67 0 8 1.33 8 4v3H4v-3c0-2.67 5.33-4 8-4m0 1.9c-2.97 0-6.1 1.46-6.1 2.1v1.1h12.2V17c0-.64-3.13-2.1-6.1-2.1"
            />
          </svg>
          <FadeTransition>
            <AccountDropdown v-show="accountDropdownOpened" />
          </FadeTransition>
        </li>
      </div>
    </ul>
  </nav>
  <FadeTransition>
    <div class="overlay" v-show="showOverlay" @click="onOverlayClick"></div>
  </FadeTransition>
</template>

<style scoped>
.overlay {
  @apply fixed top-0 right-0 left-0 bottom-0 z-20 w-full h-full bg-gray-950/80;
}

.navbar {
  @apply bg-gray-800 grid grid-cols-[6fr_1fr] px-16 relative z-30 font-main;
}

.nav-item {
  @apply px-5 py-4 relative cursor-pointer text-gray-200
  flex items-center gap-1 select-none transition-colors hover:bg-gray-900;
}

.nav-actions {
  @apply flex;
}

.nav-menu {
  @apply flex;
}

.logo {
  @apply h-[60px] w-[136px];
}

.premium-logo {
  color: #facc15;
  @apply w-6 h-6;
}

.premium-link {
  @apply flex gap-2;
}

.premium-link div {
  @apply flex flex-col;
}

.premium-link span {
  @apply text-[10px] w-[50px] font-semibold inline;
}

.try-free-text {
  @apply text-yellow-400;
}
</style>
