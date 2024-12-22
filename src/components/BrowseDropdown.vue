<script setup></script>

<template>
  <div class="wrapper">
    <ul class="category-list">
      <li class="category-list-item">Popular</li>
      <li class="category-list-item">New</li>
      <li class="category-list-item">Alphabetical</li>
      <li class="category-list-item">Simulcast Season</li>
      <li class="category-list-item">Release Calendar</li>
      <li class="category-list-item">Music Videos & Concerts</li>
    </ul>
    <div class="genres">
      <span class="genres-title">GENRES</span>
      <ul class="genre-list">
        <li class="genre-list-item">Action</li>
        <li class="genre-list-item">Adventure</li>
        <li class="genre-list-item">Comedy</li>
        <li class="genre-list-item">Drama</li>
        <li class="genre-list-item">Fantasy</li>
        <li class="genre-list-item">Music</li>
        <li class="genre-list-item">Romance</li>
        <li class="genre-list-item">Sci-Fi</li>
        <li class="genre-list-item">Seinen</li>
        <li class="genre-list-item">Shojo</li>
        <li class="genre-list-item">Shonen</li>
        <li class="genre-list-item">Slice of life</li>
        <li class="genre-list-item">Sports</li>
        <li class="genre-list-item">Supernatural</li>
        <li class="genre-list-item">Thriller</li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  @apply absolute top-14 flex bg-gray-900 text-gray-200 py-2 z-10;
}

.category-list {
  @apply w-56 flex flex-col bg-gray-900 text-gray-200 border-r-2 border-gray-600;
}

.category-list-item {
  @apply cursor-pointer py-2 px-4 h-10 hover:bg-gray-800;
}

.genre-list {
  @apply grid grid-cols-3;
}

.genre-list-item {
  @apply w-52 h-10 leading-10 cursor-pointer px-4 hover:bg-gray-800;
}

.genres-title {
  @apply text-gray-400 block py-2 px-4;
}
</style>
