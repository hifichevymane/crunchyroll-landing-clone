<script setup>
import StartWatchingBtn from './StartWatchingBtn.vue'
import { computed } from 'vue'

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
  ageRating: {
    type: Number,
    required: true,
  },
  dubbing: {
    type: Boolean,
    default: false,
    required: false,
  },
  genres: {
    type: Array,
    default: () => [],
    required: false,
  },
})

const genres = computed(() => props.genres.join(', '))
</script>

<template>
  <li>
    <img class="image-background" :src="props.src" :alt="props.alt" />
    <div class="slide-content">
      <div class="wrapper">
        <img class="logo" :src="props.logo" alt="Anime Logo" />
        <div class="tags">
          <div class="age-rating">
            <span>{{ ageRating }}+</span>
          </div>
          <span class="tag">{{ dubbing ? 'Sub | Dub' : 'Subtitled' }}</span>
          <span class="tag">{{ genres }}</span>
        </div>
        <p class="slide-description">{{ props.description }}</p>
        <div class="slide-buttons">
          <StartWatchingBtn>Start watching e1</StartWatchingBtn>
          <button class="emphasized-btn">
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
  @apply text-gray-300 mt-2 overflow-hidden max-h-[96px];
}

.slide-buttons {
  @apply flex gap-3 mt-7;
}

.emphasized-btn {
  @apply p-1;
}

.wishlist-icon {
  @apply w-7 h-7;
}

.wrapper {
  @apply w-1/2;
}

.tags {
  @apply flex items-center gap-1 text-gray-300 mt-2 font-bold;
}

.age-rating {
  @apply py-[.5px] px-1 bg-gray-400/40;
}

.tag {
  @apply before:content-['•_'];
}
</style>
