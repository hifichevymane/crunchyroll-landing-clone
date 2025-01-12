<script setup>
import TopNewsCard from './TopNewsCard.vue'
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
        <div class="top-news">
          <h4>Top News</h4>
          <TopNewsCard />
          <TopNewsCard />
        </div>
        <div class="latest-news">
          <h4>Latest</h4>
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

.top-news {
  @apply flex flex-col gap-3;
}
</style>
