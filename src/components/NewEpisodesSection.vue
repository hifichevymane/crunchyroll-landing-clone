<script setup></script>

<template>
  <section>
    <div class="header">
      <div class="new-episodes-heading">
        <svg
          class="video-logo"
          xmlns="http://www.w3.org/2000/svg"
          width="16"
          height="16"
          viewBox="0 0 16 16"
        >
          <path
            fill="currentColor"
            d="M0 3.75C0 2.784.784 2 1.75 2h12.5c.966 0 1.75.784 1.75 1.75v8.5A1.75 1.75 0 0 1 14.25 14H1.75A1.75 1.75 0 0 1 0 12.25Zm1.75-.25a.25.25 0 0 0-.25.25v8.5c0 .138.112.25.25.25h12.5a.25.25 0 0 0 .25-.25v-8.5a.25.25 0 0 0-.25-.25Z"
          />
          <path
            fill="currentColor"
            d="M6 10.559V5.442a.25.25 0 0 1 .379-.215l4.264 2.559a.25.25 0 0 1 0 .428l-4.264 2.559A.25.25 0 0 1 6 10.559"
          />
        </svg>
        <h2>New Episodes</h2>
      </div>
      <a href="#" class="view-release-calendar-link">
        VIEW RELEASE CALENDAR
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
          <use fill-rule="evenodd" href="#weuiArrowOutlined0" transform="rotate(-180 5.02 9.505)" />
        </svg>
      </a>
    </div>
    <div class="episodes-section">
      <h3 class="episodes-section-heading">Today</h3>
    </div>
    <div class="episodes-section">
      <h3 class="episodes-section-heading">Yesterday</h3>
    </div>
    <button class="show-more-btn">SHOW MORE</button>
  </section>
</template>

<style scoped>
section {
  @apply text-gray-50 px-12 mt-5;
}

.header {
  @apply flex justify-between;
}

.new-episodes-heading {
  @apply flex items-center gap-2 text-3xl;
}

.video-logo {
  @apply h-6 w-6;
}

.view-release-calendar-link {
  @apply flex items-center gap-2
  font-semibold text-gray-50/60
  transition-colors duration-200
  hover:text-gray-50;
}

.arrow-logo {
  @apply w-7 h-7;
}

.episodes-section {
  @apply py-3;
}

.episodes-section-heading {
  @apply text-2xl border-b-2 pb-1 border-gray-500;
}

.show-more-btn {
  @apply bg-cyan-900/70 w-full font-semibold py-2 mt-14
  hover:bg-cyan-900 transition-colors duration-300;
}
</style>
