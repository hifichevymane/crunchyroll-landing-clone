<script setup>
import SeriesCard from './SeriesCard.vue'

const seriesInfo = {
  seriesName: 'JoJo Bizarre Adventure',
  description: `
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum, culpa labore. Fugit id
    doloribus aspernatur, neque at amet labore, natus dolorem vitae unde minima illo voluptatum
    aut officia, accusamus voluptatem!
  `,
  imgSrc: '/src/assets/img/news-img-4.jpeg',
  imgAlt: 'JoJo Bizarre Adventure Series',
}

const SERIES = new Array(6).fill(seriesInfo)
</script>

<template>
  <section class="series">
    <SeriesCard v-for="(item, idx) in SERIES" :key="idx" v-bind="item" />
  </section>
</template>

<style scoped>
.series {
  @apply flex flex-col px-12 mt-16 gap-16;
}
</style>
