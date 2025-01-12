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
    <div class="description">
      <h5>{{ props.header }}</h5>
      <span class="date">{{ parsedData }}</span>
      <span class="author">by {{ props.author }}</span>
    </div>
  </div>
</template>

<style scoped>
.card {
  @apply flex gap-3 relative p-2
  bg-black hover:bg-gray-50/10
  transition-colors duration-200;
}

.card a {
  @apply absolute w-full h-full;
}

.card img {
  @apply w-[130px] h-[78px];
}

.description {
  @apply flex flex-col my-auto;
}

.description h5 {
  @apply text-lg;
}

.date,
.author {
  @apply text-xs text-gray-50/60;
}
</style>
