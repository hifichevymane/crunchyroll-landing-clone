<script setup>
const props = defineProps({
  src: {
    type: String,
    required: true,
  },
  alt: {
    type: String,
    required: true,
  },
  logo: {
    type: String,
    required: true,
  },
  description: {
    type: String,
    required: true,
  },
})
</script>

<template>
  <li>
    <img class="image-background" :src="props.src" :alt="props.alt" />
    <div class="slide-content">
      <div class="wrapper">
        <img class="logo" :src="props.logo" alt="Anime Logo" />
        <p class="slide-description">{{ props.description }}</p>
        <div class="slide-buttons">
          <a href="#" class="start-watching-btn">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
              <path
                fill="none"
                stroke="currentColor"
                stroke-linejoin="round"
                stroke-width="1.5"
                d="m5 3l16 9l-16 9z"
              />
            </svg>
            START WATCHING E1
          </a>
          <button class="wishlist-btn">
            <svg
              class="wishlist-icon"
              xmlns="http://www.w3.org/2000/svg"
              width="24"
              height="24"
              viewBox="0 0 24 24"
            >
              <path fill="currentColor" d="M5 21V3h14v18l-7-3zm2-3.05l5-2.15l5 2.15V5H7zM7 5h10z" />
            </svg>
          </button>
        </div>
      </div>
    </div>
  </li>
</template>

<style scoped>
li {
  @apply absolute inset-0;
}

.image-background {
  @apply w-full h-full object-cover object-center absolute;
}

.slide-content {
  @apply relative inset-0 w-[870px] h-full
  bg-gradient-to-r from-black/100 from-20% via-black/80 via-50% to-transparent
  flex flex-col items-start justify-center pl-14;
}

.logo {
  @apply h-[100px] w-auto object-contain;
}

.slide-description {
  @apply text-gray-300 mt-5 overflow-hidden max-h-[96px];
}

.slide-buttons {
  @apply flex gap-3 mt-7;
}

.start-watching-btn {
  @apply bg-orange-500 px-5 font-medium
  flex gap-2 items-center text-gray-900
  hover:bg-orange-400 hover:text-gray-800
  transition-colors duration-300 ease-out;
}

.wishlist-btn {
  @apply border-orange-500 text-orange-500
  bg-transparent border-2 p-1
  hover:border-orange-400 hover:text-orange-400
  transition-colors duration-300 ease-out;
}

.wishlist-icon {
  @apply w-7 h-7;
}

.wrapper {
  @apply w-1/2;
}
</style>
