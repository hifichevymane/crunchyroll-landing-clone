<script setup></script>

<template>
  <footer>
    <div class="info-sections-wrapper">
      <div class="info-section">
        <h4>Navigation</h4>
        <ul>
          <li>
            <a href="#">Browse Popular</a>
          </li>
          <li>
            <a href="#">Browse Simulcasts</a>
          </li>
          <li>
            <a href="#">Release Calendar</a>
          </li>
          <li>
            <a href="#">News</a>
          </li>
          <li>
            <a href="#">Games</a>
          </li>
        </ul>
      </div>
      <div class="info-section">
        <h4>Connect with us</h4>
        <ul>
          <li>
            <a href="#">Youtube</a>
          </li>
          <li>
            <a href="#">Facebook</a>
          </li>
          <li>
            <a href="#">X</a>
          </li>
          <li>
            <a href="#">Instagram</a>
          </li>
          <li>
            <a href="#">TikTok</a>
          </li>
        </ul>
      </div>
      <div class="info-section">
        <h4>Crunchyroll</h4>
        <ul>
          <li>
            <a href="#">Start a free trial</a>
          </li>
          <li>
            <a href="#">about</a>
          </li>
          <li>
            <a href="#">help center</a>
          </li>
          <li>
            <a href="#">terms of use</a>
          </li>
          <li>
            <a href="#">privacy policy</a>
          </li>
          <li>
            <a href="#">AdChoices</a>
          </li>
          <li>
            <a href="#">do not sell or share my personal information</a>
          </li>
          <li>
            <a href="#">cookie consent tool</a>
          </li>
          <li>
            <a href="#">press inquires</a>
          </li>
          <li>
            <a href="#">get the apps</a>
          </li>
          <li>
            <a href="#">redeem gift card</a>
          </li>
          <li>
            <a href="#">jobs</a>
          </li>
        </ul>
      </div>
      <div class="info-section">
        <h4>Account</h4>
        <ul>
          <li>
            <a href="#">Create account</a>
          </li>
          <li>
            <a href="#">Log in</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="legal-section">
      <span class="company-name">© Crunchyroll, LLC</span>
      <button class="lang-btn">
        <svg
          class="dropdown-logo"
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
        >
          <path fill="currentColor" d="m12 15l5-5H7z" />
        </svg>
        ENGLISH
      </button>
    </div>
  </footer>
</template>

<style scoped>
footer {
  @apply h-[505px] text-gray-50
  flex flex-col px-[180px] mt-20
  bg-gradient-to-b from-black to-cyan-800/60;
}

.info-sections-wrapper {
  @apply flex justify-between;
}

.info-section {
  @apply max-w-[220px];
}

h4 {
  @apply text-lg mb-2;
}

ul {
  @apply flex flex-col gap-1;
}

a {
  @apply capitalize text-gray-50/50 text-sm
  hover:underline hover:text-gray-50
  transition-all duration-150;
}

.legal-section {
  @apply border-t-[1.5px] border-gray-50/20
  flex items-center justify-between h-full mt-6;
}

.lang-btn {
  @apply p-3 text-gray-400 font-semibold
  flex gap-2 hover:bg-gray-600 hover:text-gray-50
  transition-colors duration-150;
}

.dropdown-logo {
  @apply text-gray-50;
}

.company-name {
  @apply text-gray-400 text-sm;
}
</style>
