<script setup>
import { ref } from 'vue'

const activeSlideIdx = ref(0)
const slides = ref([
  {
    src: '/src/assets/img/demon_slayer_season_3_release_slide.webp',
    alt: 'Demon Slayer Anime',
    logo: '/src/assets/img/Demon-Slayer-Logo.png',
  },
  {
    src: '/src/assets/img/Jujutsu_Kaisen.webp',
    alt: 'Jujutsu Kaisen Anime',
    logo: '/src/assets/img/Demon-Slayer-Logo.png',
  },
  {
    src: '/src/assets/img/Anime_BlueLock_Season2KeyArt.jpg',
    alt: 'Blue Lock Anime',
    logo: '/src/assets/img/Demon-Slayer-Logo.png',
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
        <img class="image-background" :src="slide.src" :alt="slide.alt" />
        <div class="slide-content">
          <img class="anime-logo" :src="slide.logo" alt="Anime Logo" />
          <p class="slide-description">
            Japan’s desire for World Cup glory leads the Japanese Football Association to launch a
            new rigorous training program to find the national team’s next striker. Three hundred
            high school players are pitted against each other
          </p>
          <div class="slide-buttons">
            <button class="start-watching-btn">
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
            </button>
            <button class="wishlist-btn">
              <svg
                class="wishlist-icon"
                xmlns="http://www.w3.org/2000/svg"
                width="24"
                height="24"
                viewBox="0 0 24 24"
              >
                <path
                  fill="currentColor"
                  d="M5 21V3h14v18l-7-3zm2-3.05l5-2.15l5 2.15V5H7zM7 5h10z"
                />
              </svg>
            </button>
          </div>
        </div>
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

.image-background {
  @apply w-full h-full object-cover object-center absolute;
}

.slide-content {
  @apply relative inset-0 w-[570px] h-full
  bg-gradient-to-r from-black/100 from-20% via-black/80 via-50% to-transparent
  flex flex-col items-start justify-center pl-14;
}

.slide-description {
  @apply text-gray-100 mt-5;
}

.slide-buttons {
  @apply flex gap-3 mt-7;
}

.start-watching-btn {
  @apply bg-orange-500 px-5 font-medium flex gap-2 items-center;
}

.wishlist-btn {
  @apply border-orange-500 text-orange-500 bg-transparent
  border-2 p-1;
}

.wishlist-icon {
  @apply w-7 h-7;
}

.anime-logo {
  @apply w-[200px];
}

.next-btn svg {
  @apply -scale-x-100;
}

.back-btn,
.next-btn {
  @apply absolute z-0 top-1/2 -translate-y-1/2
  text-white p-5 hover:text-gray-400 transition-colors duration-300;
}

.next-btn {
  @apply right-0;
}

svg {
  @apply w-[20px] h-[40px];
}

.slides-leave-from,
.slides-enter-from {
  @apply brightness-[0.2];
}

.slides-leave-from {
  @apply delay-100;
}

.slides-enter-to {
  @apply brightness-100;
}

.slides-enter-active,
.slides-leave-active {
  @apply transition-all duration-700;
}
</style>
