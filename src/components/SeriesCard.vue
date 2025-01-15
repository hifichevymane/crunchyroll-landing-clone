<script setup>
import StartWatchingBtn from './StartWatchingBtn.vue'

const props = defineProps({
  seriesName: {
    type: String,
    required: true,
  },
  dubbing: {
    type: Boolean,
    default: false,
    required: false,
  },
  description: {
    type: String,
    required: true,
  },
  imgSrc: {
    type: String,
    required: true,
  },
  imgAlt: {
    type: String,
    default: 'Series',
    required: false,
  },
})
</script>

<template>
  <div class="series-card">
    <div class="series-image-placeholder">
      <img :src="imgSrc" :alt="imgAlt" />
      <div class="series-overlay">
        <a href="#">To series</a>
      </div>
    </div>
    <div class="series-description">
      <h2>
        <a href="#">{{ props.seriesName }}</a>
      </h2>
      <span>{{ props.dubbing ? 'Sub | Dub' : 'Subtitled' }}</span>
      <p>{{ props.description }}</p>
      <div class="buttons">
        <StartWatchingBtn class="start-watching-btn">START WATCHING E1</StartWatchingBtn>
        <button class="watchlist-btn">
          <svg
            class="wishlist-icon"
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
          >
            <path fill="currentColor" d="M5 21V3h14v18l-7-3zm2-3.05l5-2.15l5 2.15V5H7zM7 5h10z" />
          </svg>
          ADD TO WATCHLIST
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.series-card {
  @apply flex text-gray-50 h-[360px] gap-8;
}

.series-image-placeholder {
  @apply h-full w-[650px] shrink-0 relative;
}

.series-overlay {
  @apply absolute inset-0 w-full h-full
  bg-black/50
  opacity-0 hover:opacity-100 transition-opacity
  duration-200;
}

.series-overlay a {
  @apply uppercase w-full h-full
  flex justify-center items-center text-lg;
}

.series-image-placeholder img {
  @apply h-full w-full object-cover;
}

.series-description {
  @apply flex flex-col gap-3 my-auto;
}

.series-description h2 {
  @apply text-3xl hover:underline;
}

.series-description span {
  @apply text-sm text-gray-50/60;
}

.buttons {
  @apply flex gap-3 mt-3;
}

.watchlist-btn {
  @apply flex font-semibold items-center
  gap-1 justify-center
  h-[40px] w-[220px]
  border-orange-500 text-orange-500
  bg-transparent border-2 p-1
  hover:border-orange-400 hover:text-orange-400
  transition-colors duration-300 ease-out;
}

.watchlist-btn svg {
  @apply w-7 h-7;
}
</style>
