<script setup>
import newsFirstImg from '../assets/img/news-img-1.jpeg'
import newsSecondImg from '../assets/img/news-img-2.jpeg'

import TopNewsCard from './TopNewsCard.vue'
import LatestNewsCard from './LatestNewsCard.vue'

const TOP_NEWS = [
  {
    imgSrc: newsFirstImg,
    imgAlt: 'Pizdec',
    header: 'Here’s the Exact Time The Apothecary Diaries Season 2 Premieres on Crunchyroll',
    date: new Date(),
    author: 'John Doe',
  },
  {
    imgSrc: newsFirstImg,
    imgAlt: 'Pizdec',
    header: 'Here’s the Exact Time The Apothecary Diaries Season 2 Premieres on Crunchyroll',
    date: new Date(),
    author: 'John Doe',
  },
]

const LATEST_NEWS = [
  {
    imgSrc: newsSecondImg,
    imgAlt: 'Solo Leveling News',
    header: 'Solo Leveling Season 2 Anime Unveils Iron Shadow Visual',
    date: new Date(),
    author: 'John Doe',
  },
  {
    imgSrc: newsSecondImg,
    imgAlt: 'Solo Leveling News',
    header: 'Solo Leveling Season 2 Anime Unveils Iron Shadow Visual',
    date: new Date(),
    author: 'John Doe',
  },
  {
    imgSrc: newsSecondImg,
    imgAlt: 'Solo Leveling News',
    header: 'Solo Leveling Season 2 Anime Unveils Iron Shadow Visual',
    date: new Date(),
    author: 'John Doe',
  },
  {
    imgSrc: newsSecondImg,
    imgAlt: 'Solo Leveling News',
    header: 'Solo Leveling Season 2 Anime Unveils Iron Shadow Visual',
    date: new Date(),
    author: 'John Doe',
  },
  {
    imgSrc: newsSecondImg,
    imgAlt: 'Solo Leveling News',
    header: 'Solo Leveling Season 2 Anime Unveils Iron Shadow Visual',
    date: new Date(),
    author: 'John Doe',
  },
  {
    imgSrc: newsSecondImg,
    imgAlt: 'Solo Leveling News',
    header: 'Solo Leveling Season 2 Anime Unveils Iron Shadow Visual',
    date: new Date(),
    author: 'John Doe',
  },
]
</script>

<template>
  <section>
    <div class="wrapper">
      <div class="header-wrapper">
        <div>
          <svg
            class="news-logo"
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="0 0 24 24"
          >
            <path
              fill="currentColor"
              d="M12 8H4a2 2 0 0 0-2 2v4a2 2 0 0 0 2 2h1v4a1 1 0 0 0 1 1h2a1 1 0 0 0 1-1v-4h3l5 4V4zm3 7.6L13 14H4v-4h9l2-1.6zm6.5-3.6c0 1.71-.96 3.26-2.5 4V8c1.53.75 2.5 2.3 2.5 4"
            />
          </svg>
          <h2>News Collection</h2>
        </div>
        <a href="#">
          VIEW ALL
          <svg
            class="arrow-logo"
            xmlns="http://www.w3.org/2000/svg"
            width="24"
            height="24"
            viewBox="-6 0 24 24"
          >
            <defs>
              <path
                id="weuiArrowOutlined0"
                fill="currentColor"
                d="m7.588 12.43l-1.061 1.06L.748 7.713a.996.996 0 0 1 0-1.413L6.527.52l1.06 1.06l-5.424 5.425z"
              />
            </defs>
            <use
              fill-rule="evenodd"
              href="#weuiArrowOutlined0"
              transform="rotate(-180 5.02 9.505)"
            />
          </svg>
        </a>
      </div>
      <div class="content">
        <div class="news-category-section">
          <h4>Top News</h4>
          <TopNewsCard v-for="(item, idx) in TOP_NEWS" :key="idx" v-bind="item" />
        </div>
        <div class="news-category-section">
          <h4>Latest</h4>
          <LatestNewsCard v-for="(item, idx) in LATEST_NEWS" :key="idx" v-bind="item" />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
section {
  @apply text-gray-50 py-6 px-12 bg-teal-500;
}

.wrapper {
  @apply bg-black px-8 py-6;
}

.header-wrapper {
  @apply flex items-center gap-1 justify-between;
}

.header-wrapper div,
.header-wrapper a {
  @apply flex;
}

.header-wrapper a {
  @apply flex gap-3 font-semibold
  text-gray-50/70 hover:text-gray-50
  transition-colors duration-200;
}

.news-logo {
  @apply w-8 h-8;
}

h2 {
  @apply text-3xl;
}

h4 {
  @apply text-lg;
}

.content {
  @apply grid grid-cols-[minmax(0,_1fr)_minmax(0,_3fr)]
  mt-5 gap-5;
}

.news-category-section {
  @apply flex flex-col gap-3;
}
</style>
