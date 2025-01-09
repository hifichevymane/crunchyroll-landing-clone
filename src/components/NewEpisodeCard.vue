<script setup>
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  episodeNumber: {
    type: Number,
    required: true,
  },
  duration: {
    type: String,
    required: true,
  },
  previewImgSrc: {
    type: String,
    required: true,
  },
  dubbing: {
    type: Boolean,
    required: false,
  },
})
</script>

<template>
  <div class="card">
    <a href="#" class="episode-link"></a>
    <img class="episode-image" :src="props.previewImgSrc" alt="Episode Preview" />
    <div class="episode-info">
      <h4 class="episode-title">{{ props.title }}</h4>
      <span class="episode-number">Episode {{ props.episodeNumber }}</span>
      <div class="episode-type-duration-wrapper">
        <span class="episode-type">{{ dubbing ? 'Sub | Dub' : 'Subtitled' }}</span>
        <span class="episode-duration">{{ duration }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  @apply w-full h-[82px] flex gap-3
  bg-black hover:bg-gray-500/20
  transition-colors duration-200
  relative;
}

.episode-image {
  @apply w-[145px] h-full bg-white shrink-0 object-cover;
}

.episode-info {
  @apply flex flex-col justify-center w-full mr-3;
}

.episode-duration {
  @apply text-sm text-teal-500;
}

.episode-title {
  @apply text-base;
}

.episode-number,
.episode-type {
  @apply text-gray-400 text-sm;
}

.episode-type-duration-wrapper {
  @apply flex justify-between w-full items-center mt-[2px];
}

.episode-link {
  @apply absolute w-full h-full;
}
</style>
