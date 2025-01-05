<script setup>
import CarouselSlide from './CarouselSlide.vue'
import slideContent from '../assets/slide-content.json'

import { ref } from 'vue'
import { useIntervalFn } from '@vueuse/core'

const slides = ref(slideContent)
const activeSlideIdx = ref(0)

const { pause, resume } = useIntervalFn(() => {
  if (activeSlideIdx.value < slides.value.length - 1) {
    activeSlideIdx.value++
  } else {
    activeSlideIdx.value = 0
  }
}, 5000)

const onBackBtnClick = () => {
  pause()
  if (activeSlideIdx.value > 0) {
    activeSlideIdx.value--
  } else {
    activeSlideIdx.value = slides.value.length - 1
  }
  resume()
}

const onNextBtnClick = () => {
  pause()
  if (activeSlideIdx.value < slides.value.length - 1) {
    activeSlideIdx.value++
  } else {
    activeSlideIdx.value = 0
  }
  resume()
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
      <CarouselSlide
        v-for="(slide, key) in slides"
        :key="key"
        v-bind="slide"
        v-show="key === activeSlideIdx"
      />
    </TransitionGroup>
    <div class="slide-pagination-buttons">
      <div v-for="slide in slides" :key="slide.src" class="slide-pagination-btn"></div>
    </div>
  </ul>
</template>

<style scoped>
.carousel {
  @apply relative h-[700px];
}

.next-btn svg {
  @apply -scale-x-100;
}

.back-btn,
.next-btn {
  @apply absolute z-10 top-1/2 -translate-y-1/2
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

.slide-pagination-buttons {
  @apply flex mt-6 h-3 w-[250px] gap-3
  absolute bottom-40 pl-14;
}

.slide-pagination-btn {
  @apply bg-white h-full w-6
  cursor-pointer rounded-2xl flex-grow
  hover:bg-orange-500 opacity-80
  transition-colors duration-300;
}
</style>
