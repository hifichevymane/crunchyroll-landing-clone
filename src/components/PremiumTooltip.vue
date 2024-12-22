<script setup></script>

<template>
  <div class="tooltip">
    <div class="premium-trial-header">
      <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
        <path
          fill="none"
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="1.5"
          d="M19.2 17L21 7l-6.3 3L12 7l-2.7 3L3 7l1.8 10z"
        />
      </svg>
      <h3>7-Day Free Trial</h3>
    </div>
    <p>
      Premium access includes unlimited anime, no ads, and new episodes shortly after they air in
      Japan. Try it now!
    </p>
  </div>
</template>

<style scoped>
.tooltip {
  @apply absolute top-[65px] bg-gray-900 w-[360px] h-fit -translate-x-[35%] py-7 px-5 text-gray-50;
}

.tooltip h3,
.tooltip p {
  @apply text-center;
}

.tooltip h3 {
  @apply text-xl font-bold;
}

.tooltip p {
  @apply text-sm;
}

.premium-trial-header {
  @apply flex items-center justify-center gap-2 mb-3;
}
</style>
