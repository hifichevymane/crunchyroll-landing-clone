<script setup>
import { ref } from 'vue'

const DROPDOWN_ID = 'dropdown'
const popoverOpened = ref(false)
</script>

<template>
  <button
    class="lang-btn"
    :class="popoverOpened && 'active-btn'"
    :popovertarget="DROPDOWN_ID"
    @click="popoverOpened = !popoverOpened"
  >
    <svg
      class="dropdown-logo"
      xmlns="http://www.w3.org/2000/svg"
      width="24"
      height="24"
      viewBox="0 0 24 24"
    >
      <path fill="currentColor" d="m12 15l5-5H7z" />
    </svg>
    ENGLISH
  </button>
  <ul :id="DROPDOWN_ID" class="dropdown" popover="manual">
    <li class="language">Ukrainian</li>
    <li class="language">Russian</li>
    <li class="language active">English</li>
    <li class="language">Bulgarian</li>
    <li class="language">French</li>
    <li class="language">Chinese</li>
  </ul>
</template>

<style scoped>
.dropdown-container {
  @apply relative;
}

.lang-btn {
  @apply p-3 text-gray-400 font-semibold
  flex gap-2 hover:bg-gray-800 hover:text-gray-50
  transition-colors duration-150;
}

.active-btn {
  @apply bg-gray-800 text-gray-50;
}

.lang-btn {
  anchor-name: --lang-btn;
}

.dropdown {
  @apply bg-gray-800 max-h-[230px]
  overflow-y-scroll py-4 absolute inset-auto;
}

.dropdown {
  position-anchor: --lang-btn;
  top: anchor(bottom);
  right: anchor(right);
  transform: translateY(calc(calc(100% + 48px) * -1));
}

.language {
  @apply w-[200px] py-3 px-5 hover:bg-black/40
  transition-colors duration-200 cursor-pointer text-sm
  text-gray-400;
}

.active {
  @apply text-gray-50;
}

.dropdown-logo {
  @apply text-gray-50;
}
</style>
