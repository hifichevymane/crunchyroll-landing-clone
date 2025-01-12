<script setup>
import { computed } from 'vue'
import { formatDate } from '@/utils'

const props = defineProps({
  imgSrc: {
    type: String,
    required: true,
  },
  imgAlt: {
    type: String,
    default: 'Anime Top News',
    required: false,
  },
  header: {
    type: String,
    required: true,
  },
  date: {
    type: Date,
    required: true,
  },
  author: {
    type: String,
    required: true,
  },
})

const parsedData = computed(() => formatDate(props.date))
</script>

<template>
  <div class="card">
    <a href="#"></a>
    <img :src="props.imgSrc" :alt="props.imgAlt" />
    <h5>{{ props.header }}</h5>
    <span class="date">{{ parsedData }}</span>
    <span class="author">by {{ props.author }}</span>
  </div>
</template>

<style scoped>
.card {
  @apply flex flex-col relative
  w-full p-2 bg-black
  hover:bg-gray-50/10
  transition-colors duration-200;
}

.card a {
  @apply absolute w-full h-full;
}

.card img {
  @apply w-full;
}

.card h5 {
  @apply text-xl my-3;
}

.date,
.author {
  @apply text-gray-50/60 text-sm;
}
</style>
