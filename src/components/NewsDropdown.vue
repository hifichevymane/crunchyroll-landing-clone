<script setup></script>

<template>
  <ul class="dropdown">
    <li class="dropdown-item">All News</li>
    <li class="dropdown-item">Anime Awards</li>
    <li class="dropdown-item">Events & Experiences</li>
  </ul>
</template>

<style scoped>
.dropdown {
  @apply absolute top-14 left-0 bg-gray-900;
}

.dropdown-item {
  @apply w-72 h-10 leading-10 cursor-pointer pl-5;
}
</style>
