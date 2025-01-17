<script setup></script>

<template>
  <div class="still-looking-for-section">
    <h3 class="still-looking-for-text">
      Still looking for something to watch?
      <br />
      Check out our full library
    </h3>
    <a href="#" class="emphasized-btn">view all</a>
  </div>
</template>

<style scoped>
.still-looking-for-section {
  @apply flex justify-center items-center
  flex-col gap-5 mt-[80px] relative;
}

.still-looking-for-text {
  @apply text-gray-50 text-xl
  font-semibold text-center;
}
</style>
