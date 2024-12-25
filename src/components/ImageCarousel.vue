<script setup>
import { ref } from 'vue'

const activeSlideIdx = ref(0)
const slides = ref([
  {
    src: '/src/assets/img/demon_slayer_season_3_release_slide.webp',
    alt: 'Demon Slayer Anime',
  },
  {
    src: '/src/assets/img/Jujutsu_Kaisen.webp',
    alt: 'Jujutsu Kaisen Anime',
  },
  {
    src: '/src/assets/img/Anime_BlueLock_Season2KeyArt.jpg',
    alt: 'Blue Lock Anime',
  },
])

const onBackBtnClick = () => {
  if (activeSlideIdx.value > 0) {
    activeSlideIdx.value--
  } else {
    activeSlideIdx.value = slides.value.length - 1
  }
}

const onNextBtnClick = () => {
  if (activeSlideIdx.value < slides.value.length - 1) {
    activeSlideIdx.value++
  } else {
    activeSlideIdx.value = 0
  }
}
</script>

<template>
  <ul class="carousel">
    <button class="back-btn" @click="onBackBtnClick">
      <svg xmlns="http://www.w3.org/2000/svg" width="12" height="24" viewBox="0 0 12 24">
        <path
          fill="currentColor"
          fill-rule="evenodd"
          d="m3.343 12l7.071 7.071L9 20.485l-7.778-7.778a1 1 0 0 1 0-1.414L9 3.515l1.414 1.414z"
        />
      </svg>
    </button>
    <button class="next-btn" @click="onNextBtnClick">
      <svg xmlns="http://www.w3.org/2000/svg" width="12" height="24" viewBox="0 0 12 24">
        <path
          fill="currentColor"
          fill-rule="evenodd"
          d="m3.343 12l7.071 7.071L9 20.485l-7.778-7.778a1 1 0 0 1 0-1.414L9 3.515l1.414 1.414z"
        />
      </svg>
    </button>
    <TransitionGroup name="slides">
      <li v-for="(slide, key) in slides" :key="key" v-show="key === activeSlideIdx">
        <img :src="slide.src" :alt="slide.alt" />
      </li>
    </TransitionGroup>
  </ul>
</template>

<style scoped>
.carousel {
  @apply relative h-[700px];
}

.carousel li {
  @apply absolute inset-0 -z-10;
}

.carousel img {
  @apply w-full h-full object-cover object-center absolute;
}

.next-btn svg {
  @apply -scale-x-100;
}

.back-btn,
.next-btn {
  @apply absolute z-0 top-1/2 -translate-y-1/2 text-white p-5 hover:text-gray-300;
}

.next-btn {
  @apply right-0;
}

svg {
  @apply w-[20px] h-[40px];
}

.slides-enter-from {
  @apply brightness-[0.2];
}

.slides-enter-to {
  @apply brightness-100;
}

.slides-enter-active,
.slides-leave-active {
  @apply transition-all duration-500;
}
</style>
