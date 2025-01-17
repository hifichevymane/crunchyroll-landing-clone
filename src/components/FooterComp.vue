<script setup>
import LangDropdown from './LangDropdown.vue'
</script>

<template>
  <footer>
    <div class="info-sections-wrapper">
      <div class="info-section">
        <h4>Navigation</h4>
        <ul class="info-section-links">
          <li>
            <a href="#" class="footer-link">Browse Popular</a>
          </li>
          <li>
            <a href="#" class="footer-link">Browse Simulcasts</a>
          </li>
          <li>
            <a href="#" class="footer-link">Release Calendar</a>
          </li>
          <li>
            <a href="#" class="footer-link">News</a>
          </li>
          <li>
            <a href="#" class="footer-link">Games</a>
          </li>
        </ul>
      </div>
      <div class="info-section">
        <h4>Connect with us</h4>
        <ul class="info-section-links">
          <li>
            <a href="#" class="footer-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                <path
                  fill="currentColor"
                  d="m10 15l5.19-3L10 9zm11.56-7.83c.13.47.22 1.1.28 1.9c.07.8.1 1.49.1 2.09L22 12c0 2.19-.16 3.8-.44 4.83c-.25.9-.83 1.48-1.73 1.73c-.47.13-1.33.22-2.65.28c-1.3.07-2.49.1-3.59.1L12 19c-4.19 0-6.8-.16-7.83-.44c-.9-.25-1.48-.83-1.73-1.73c-.13-.47-.22-1.1-.28-1.9c-.07-.8-.1-1.49-.1-2.09L2 12c0-2.19.16-3.8.44-4.83c.25-.9.83-1.48 1.73-1.73c.47-.13 1.33-.22 2.65-.28c1.3-.07 2.49-.1 3.59-.1L12 5c4.19 0 6.8.16 7.83.44c.9.25 1.48.83 1.73 1.73"
                />
              </svg>
              Youtube
            </a>
          </li>
          <li>
            <a href="#" class="footer-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                <path
                  fill="currentColor"
                  fill-rule="evenodd"
                  d="M15.725 22v-7.745h2.6l.389-3.018h-2.99V9.31c0-.874.243-1.47 1.497-1.47h1.598v-2.7a21 21 0 0 0-2.33-.12c-2.304 0-3.881 1.407-3.881 3.99v2.227H10v3.018h2.607V22H3.104C2.494 22 2 21.506 2 20.896V3.104C2 2.494 2.494 2 3.104 2h17.792C21.506 2 22 2.494 22 3.104v17.792c0 .61-.494 1.104-1.104 1.104z"
                />
              </svg>
              Facebook
            </a>
          </li>
          <li>
            <a href="#" class="footer-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 16 16">
                <path
                  fill="currentColor"
                  d="M9.294 6.928L14.357 1h-1.2L8.762 6.147L5.25 1H1.2l5.31 7.784L1.2 15h1.2l4.642-5.436L10.751 15h4.05zM7.651 8.852l-.538-.775L2.832 1.91h1.843l3.454 4.977l.538.775l4.491 6.47h-1.843z"
                />
              </svg>
              X
            </a>
          </li>
          <li>
            <a href="#" class="footer-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                <path
                  fill="currentColor"
                  d="M7.8 2h8.4C19.4 2 22 4.6 22 7.8v8.4a5.8 5.8 0 0 1-5.8 5.8H7.8C4.6 22 2 19.4 2 16.2V7.8A5.8 5.8 0 0 1 7.8 2m-.2 2A3.6 3.6 0 0 0 4 7.6v8.8C4 18.39 5.61 20 7.6 20h8.8a3.6 3.6 0 0 0 3.6-3.6V7.6C20 5.61 18.39 4 16.4 4zm9.65 1.5a1.25 1.25 0 0 1 1.25 1.25A1.25 1.25 0 0 1 17.25 8A1.25 1.25 0 0 1 16 6.75a1.25 1.25 0 0 1 1.25-1.25M12 7a5 5 0 0 1 5 5a5 5 0 0 1-5 5a5 5 0 0 1-5-5a5 5 0 0 1 5-5m0 2a3 3 0 0 0-3 3a3 3 0 0 0 3 3a3 3 0 0 0 3-3a3 3 0 0 0-3-3"
                />
              </svg>
              Instagram
            </a>
          </li>
          <li>
            <a href="#" class="footer-link">
              <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24">
                <path
                  fill="currentColor"
                  d="M18.857 3H5.143A2.145 2.145 0 0 0 3 5.143v13.714C3 20.04 3.961 21 5.143 21h13.714A2.145 2.145 0 0 0 21 18.857V5.143A2.145 2.145 0 0 0 18.857 3m-1.712 7.853a3.17 3.17 0 0 1-1.822-.371a3.2 3.2 0 0 1-1.16-1.066v4.944a3.654 3.654 0 1 1-3.654-3.654c.076 0 .15.007.225.011v1.801c-.075-.009-.148-.023-.225-.023a1.865 1.865 0 1 0 0 3.73c1.03 0 1.94-.811 1.94-1.841l.018-8.398h1.723a3.21 3.21 0 0 0 2.957 2.865v2.002"
                />
              </svg>
              TikTok
            </a>
          </li>
        </ul>
      </div>
      <div class="info-section">
        <h4>Crunchyroll</h4>
        <ul class="info-section-links">
          <li>
            <a href="#" class="footer-link">Start a free trial</a>
          </li>
          <li>
            <a href="#" class="footer-link">about</a>
          </li>
          <li>
            <a href="#" class="footer-link">help center</a>
          </li>
          <li>
            <a href="#" class="footer-link">terms of use</a>
          </li>
          <li>
            <a href="#" class="footer-link">privacy policy</a>
          </li>
          <li>
            <a href="#" class="footer-link">AdChoices</a>
          </li>
          <li>
            <a href="#" class="footer-link">do not sell or share my personal information</a>
          </li>
          <li>
            <a href="#" class="footer-link">cookie consent tool</a>
          </li>
          <li>
            <a href="#" class="footer-link">press inquires</a>
          </li>
          <li>
            <a href="#" class="footer-link">get the apps</a>
          </li>
          <li>
            <a href="#" class="footer-link">redeem gift card</a>
          </li>
          <li>
            <a href="#" class="footer-link">jobs</a>
          </li>
        </ul>
      </div>
      <div class="info-section">
        <h4>Account</h4>
        <ul class="info-section-links">
          <li>
            <a href="#" class="footer-link">Create account</a>
          </li>
          <li>
            <a href="#" class="footer-link">Log in</a>
          </li>
        </ul>
      </div>
    </div>
    <div class="legal-section">
      <span class="company-name">© Crunchyroll, LLC</span>
      <LangDropdown />
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
  @apply text-lg mb-2 capitalize;
}

.info-section-links {
  @apply flex flex-col gap-2;
}

.footer-link {
  @apply capitalize text-gray-50/50 text-sm
  hover:underline hover:text-gray-50
  transition-all duration-150
  flex items-center gap-2;
}

.legal-section {
  @apply border-t-[1.5px] border-gray-50/20
  flex items-center justify-between h-full mt-6;
}

.lang-btn {
  @apply p-3 text-gray-400 font-semibold
  flex gap-2 hover:bg-gray-800 hover:text-gray-50
  active:bg-gray-800 active:text-gray-50
  transition-colors duration-150;
}

.dropdown-logo {
  @apply text-gray-50;
}

.company-name {
  @apply text-gray-400 text-sm;
}
</style>
