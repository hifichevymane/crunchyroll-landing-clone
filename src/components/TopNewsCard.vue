<script setup></script>

<template>
  <div class="card">
    <a href="#"></a>
    <img src="/src/assets/img/news-img-1.jpeg" alt="News Image" />
    <h5>Here’s the Exact Time The Apothecary Diaries Season 2 Premieres on Crunchyroll</h5>
    <span class="date">date</span>
    <span class="author">by John Doe</span>
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
