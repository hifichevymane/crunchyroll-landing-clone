<script setup>
import CarouselSlide from './CarouselSlide.vue'
import PreviousSlideBtn from './PreviousSlideBtn.vue'
import NextSlideBtn from './NextSlideBtn.vue'

import slideContent from '@/slide-content'

import { ref, watch } from 'vue'
import { useIntervalFn } from '@vueuse/core'

const INIT_SLIDE_DURATION_MS = 5000
const SLIDE_PROGRESS_BAR_UPDATE_INTERVAL_MS = 50
const PROGRESS_BAR_STEP = (SLIDE_PROGRESS_BAR_UPDATE_INTERVAL_MS / INIT_SLIDE_DURATION_MS) * 100

const slideDurationMs = ref(INIT_SLIDE_DURATION_MS)
const progressBarWidth = ref(0)
const slides = ref(slideContent)
const activeSlideIdx = ref(0)

const changeSlideInterval = useIntervalFn(() => {
  if (activeSlideIdx.value < slides.value.length - 1) {
    activeSlideIdx.value++
  } else {
    activeSlideIdx.value = 0
  }
}, slideDurationMs)

const progressBarInterval = useIntervalFn(() => {
  progressBarWidth.value += PROGRESS_BAR_STEP
  if (progressBarWidth.value > 100) {
    progressBarWidth.value = 100
    progressBarInterval.pause()
  }
}, SLIDE_PROGRESS_BAR_UPDATE_INTERVAL_MS)

const onBackBtnClick = () => {
  changeSlideInterval.pause()

  if (activeSlideIdx.value > 0) {
    activeSlideIdx.value--
  } else {
    activeSlideIdx.value = slides.value.length - 1
  }

  changeSlideInterval.resume()
}

const onNextBtnClick = () => {
  changeSlideInterval.pause()

  if (activeSlideIdx.value < slides.value.length - 1) {
    activeSlideIdx.value++
  } else {
    activeSlideIdx.value = 0
  }

  changeSlideInterval.resume()
}

const pauseSlideTimer = () => {
  changeSlideInterval.pause()
  progressBarInterval.pause()
  const elapsedTime = INIT_SLIDE_DURATION_MS * (progressBarWidth.value / 100)
  slideDurationMs.value = INIT_SLIDE_DURATION_MS - elapsedTime
}

const resumeSlideTimer = () => {
  changeSlideInterval.resume()
  progressBarInterval.resume()
}

watch(activeSlideIdx, () => {
  slideDurationMs.value = INIT_SLIDE_DURATION_MS
  progressBarWidth.value = 0
})
</script>

<template>
  <section>
    <ul class="carousel">
      <PreviousSlideBtn @click="onBackBtnClick" />
      <NextSlideBtn @click="onNextBtnClick" />
      <CarouselSlide
        v-for="(slide, key) in slides"
        :key="key"
        v-bind="slide"
        :active="key === activeSlideIdx"
        @slide-content-mouseenter="pauseSlideTimer"
        @slide-content-mouseleave="resumeSlideTimer"
      />
      <div class="slide-pagination-buttons">
        <div
          v-for="(slide, idx) in slides"
          :key="idx"
          class="slide-pagination-btn"
          :class="{ 'active-slide-pagination-btn': idx === activeSlideIdx }"
          @click="activeSlideIdx = idx"
          @mouseenter="pauseSlideTimer"
          @mouseleave="resumeSlideTimer"
        >
          <div
            class="slide-progress-bar"
            :style="{ width: idx === activeSlideIdx ? `${progressBarWidth}%` : '0%' }"
          ></div>
        </div>
      </div>
    </ul>
  </section>
</template>

<style scoped>
.carousel {
  @apply relative h-[700px];
}

.slide-pagination-buttons {
  @apply flex mt-6 h-3 w-[250px] gap-3
  absolute bottom-32 pl-14;
}

.slide-pagination-btn {
  @apply bg-gray-400/50 h-full w-6
  cursor-pointer rounded-2xl flex-grow
  hover:bg-orange-800
  transition-colors duration-300 overflow-hidden;
}

.active-slide-pagination-btn {
  @apply hover:bg-orange-500;
}

.slide-progress-bar {
  @apply w-0 h-[100%] bg-orange-500 rounded-2xl;
}
</style>
