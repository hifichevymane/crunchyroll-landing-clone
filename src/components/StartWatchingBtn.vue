<script setup></script>

<template>
  <a href="#">
    <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
      <path
        fill="none"
        stroke="currentColor"
        stroke-linejoin="round"
        stroke-width="1.5"
        d="m5 3l16 9l-16 9z"
      />
    </svg>
    <slot></slot>
  </a>
</template>

<style scoped>
a {
  @apply bg-orange-500 px-5 font-semibold
  flex gap-2 items-center text-gray-900
  hover:bg-orange-400 hover:text-gray-800
  transition-colors duration-300 ease-out h-[40px] w-[240px];
}
</style>
