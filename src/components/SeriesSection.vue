<script setup>
import SeriesCard from './SeriesCard.vue'
</script>

<template>
  <section class="series">
    <SeriesCard />
    <SeriesCard />
    <SeriesCard />
    <SeriesCard />
  </section>
</template>

<style scoped>
.series {
  @apply flex flex-col px-12 mt-16 gap-16;
}
</style>
