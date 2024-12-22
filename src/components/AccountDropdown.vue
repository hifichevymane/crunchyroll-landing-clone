<script setup></script>

<template>
  <div class="dropdown">
    <div class="dropdown-item">
      <span class="header">Create Account</span>
      <span class="description">Join for free or go Premium.</span>
    </div>
    <div class="dropdown-item">
      <span class="header">Log In</span>
      <span class="description">Already joined Crunchyroll? Welcome back!</span>
    </div>
    <div class="dropdown-item">
      <span class="header">Gift Card</span>
      <span class="description">Have a gift card? Redeem it here.</span>
    </div>
    <button class="premium-trial-btn">
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
      7-DAY FREE TRIAL
    </button>
  </div>
</template>

<style scoped>
.dropdown {
  @apply absolute top-14 right-0
  flex flex-col w-[388px]
  bg-gray-900 text-gray-200
  py-4;
}

.dropdown-item {
  @apply px-6 py-4 hover:bg-gray-800;
}

.header,
.description {
  @apply block;
}

.header {
  @apply text-base;
}

.description {
  @apply text-sm text-gray-400;
}

.premium-trial-btn {
  @apply bg-yellow-500 text-gray-900 py-3 mt-4 mx-4 font-bold
  flex items-center justify-center gap-1
  transition-colors duration-150 hover:bg-yellow-400;
}
</style>
