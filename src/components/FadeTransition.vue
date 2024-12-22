<script setup></script>

<template>
  <Transition name="fade">
    <slot></slot>
  </Transition>
</template>

<style scoped>
.fade-enter-from,
.fade-leave-to {
  @apply opacity-0;
}

.fade-enter-to,
.fade-leave-from {
  @apply opacity-100;
}

.fade-enter-active,
.fade-leave-active {
  @apply transition-opacity duration-200;
}
</style>
