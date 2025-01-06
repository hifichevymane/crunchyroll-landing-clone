<script setup>
const emit = defineEmits(['click'])
</script>

<template>
  <button @click="emit('click')">
    <svg xmlns="http://www.w3.org/2000/svg" width="12" height="24" viewBox="0 0 12 24">
      <path
        fill="currentColor"
        fill-rule="evenodd"
        d="m3.343 12l7.071 7.071L9 20.485l-7.778-7.778a1 1 0 0 1 0-1.414L9 3.515l1.414 1.414z"
      />
    </svg>
  </button>
</template>

<style scoped>
button {
  @apply absolute z-10 top-1/2 -translate-y-1/2
  text-white p-5 hover:text-gray-400
  transition-colors duration-300 right-0;
}

svg {
  @apply w-[20px] h-[40px] -scale-x-100;
}
</style>
