<script setup>
import NavBar from './components/NavBar.vue'
import ImageCarousel from './components/ImageCarousel.vue'
import NewEpisodesSection from './components/NewEpisodesSection.vue'
import NewsCollectionSection from './components/NewsCollectionSection.vue'
import SeriesSection from './components/SeriesSection.vue'
import FooterComp from './components/FooterComp.vue'
import StillLookingForComp from './components/StillLookingForComp.vue'
</script>

<template>
  <main>
    <NavBar />
    <ImageCarousel />
    <NewEpisodesSection />
    <NewsCollectionSection />
    <SeriesSection />
    <StillLookingForComp />
  </main>
  <FooterComp />
</template>

<style scoped></style>
