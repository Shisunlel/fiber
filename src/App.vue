<template>
  <button @click="toggleDark" class="fixed h-15 w-15 bottom-8 right-8 bg-teal-700 dark:bg-teal-600 transition-colors duration-1000 text-white p-2 rounded-full hover:bg-teal-800">
    <svg id="light-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 hidden">
      <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-4.773-4.227l-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z" />
    </svg>
    <svg id="dark-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 hidden">
      <path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" />
    </svg>
  </button>
  <header class="p-8 sm:py-4 sm:px-16 2xl:px-80">
    <nav>
      <div class="flex items-center justify-between">
          <div>
            <a href="/" class="text-2xl font-extrabold">Fiber</a>
          </div>
          <ul class="hidden sm:flex gap-8">
            <li>Community</li>
            <li>Pricing</li>
            <li>Features</li>
          </ul>
          <div class="hidden sm:flex items-center gap-8">
            <a href="/fiber/auth/" class="font-bold">Sign In</a>
            <button @click="goToAuth" class="main-bg text-white">Sign Up</button>
          </div>
          <div class="block sm:hidden cursor-pointer" @click="toggleNav">
            <svg class="text-black dark:text-white transition-colors duration-1000" width="24" height="20" viewBox="0 0 24 20" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M24 4H0V0H24V4ZM24 8H0V12H24V8ZM24 16H0V20H24V16Z" fill="currentColor"/>
            </svg>
          </div>
      </div>
      <div class="sm:hidden text-left pt-4 transition-all duration-150" id="mobile-nav" style="opacity: 0; height: 0;">
        <ul class="flex flex-col gap-2">
          <li>Community</li>
          <li>Pricing</li>
          <li>Features</li>
          <li>Sign In</li>
          <li><a href="/fiber/auth/">Sign Up</a></li>
        </ul>
      </div>
    </nav>
    <div class="flex flex-col sm:flex-row gap-4 pb-4 sm:pt-14 items-center justify-between">
      <img class="w-full order-1 sm:order-2" src="./assets/hero-Illustration.png" alt="">
      <div class="order-2 sm:order-1 flex flex-col gap-4">
        <div class="rating hidden sm:flex sm:gap-3">
          <div class="star-container flex">
            <img src="./assets/star.svg" alt="">
            <img src="./assets/star.svg" alt="">
            <img src="./assets/star.svg" alt="">
            <img src="./assets/star.svg" alt="">
            <img src="./assets/star.svg" alt="">
          </div>
          <p>Rated 4.8/5 (243 reviews)</p>
        </div>
        <h1 class="heading">Create your portfolio in minutes.</h1>
        <p class="text-left text-lg dark:text-slate-100">With Fiber, you can setup your own personal portfolio in minutes with dozens of premade, beautiful templates.</p>
        <div class="flex flex-col gap-4 sm:flex-row sm:gap-8 items-center">
          <button class="main-bg text-white self-stretch lg:self-start">Start Free Trial</button>
          <a href="#" class="underline main-text font-bold">View Examples</a>
        </div>
        <ul class="flex flex-col sm:flex-row gap-2 sm:gap-4">
          <li class="flex gap-2 items-center">
            <img src="./assets/Checkmark.svg" alt="">
            No Credit Card Required
          </li>
          <li class="flex gap-2 items-center">
            <img src="./assets/Checkmark.svg" alt="">
            10 Free Templates
          </li>
        </ul>
      </div>
    </div>
  </header>
  <main class="bg-white dark:bg-stone-800 transition-colors duration-1000  px-8 py-16 sm:px-16 2xl:px-80">
    <section id="why-us" class="text-left">
      <span class="main-text font-bold">Why Fiber?</span>
      <h1 class="heading pt-4 pb-6 max-w-xl">A good portfolio means good employability.</h1>
      <div id="features" class="text-inherit grid lg:grid-cols-3 lg:gap-6">
        <div class="py-4 flex flex-col gap-3">
          <img src="./assets/time.svg" class="w-9" alt="">
          <strong>Build in minutes</strong>
          <p class="w-[97%]">With a selection of premade templates, you can build out a portfolio in less than 10 minutes.</p>
        </div>
        <div class="py-4 flex flex-col gap-3">
          <img src="./assets/code.svg" class="w-9" alt="">
          <strong>Add custom css</strong>
          <p class="w-[95%]">Customize your personal portfolio even more with the ability to add your own custom CSS styles.</p>
        </div>
        <div class="py-4 flex flex-col gap-3">
          <img src="./assets/allSizes.svg" class="w-9" alt="">
          <strong>Responsive</strong>
          <p>All Fiber templates are fully responsive to ensure the experience is seemless across all devices.</p>
        </div>
      </div>
    </section>
    <section id="portfolio" class="text-left text-white my-16 pt-8 px-8 lg:pt-3 lg:px-12 main-bg rounded-lg flex flex-col lg:flex-row gap-4 items-center">
      <div class="flex flex-col gap-4">
        <h1 class="heading">Diversify your portfolio.</h1>
        <p class="w-[95%] lg:w-[75%] font-light">Create an even more impressive portfolio by creating case studies for your projects. Simply follow our step-by-step guide.</p>
        <button class="bg-white text-indigo-700 font-extrabold self-stretch lg:self-start">Start Free Trial</button>
      </div>
      <div class="mt-7 h-80 lg:h-full max-w-xl flex-grow">
        <img class="object-cover rounded-t h-full w-full" src="./assets/Page_Image.png" alt="">
      </div>
    </section>
    <section id="testimonial" class="flex flex-col lg:flex-row gap-6">
      <div class="flex flex-col gap-4 text-left border border-slate-300 dark:border-none dark:bg-indigo-500 rounded p-5 mb-10 lg:mb-0 transition-colors duration-1000 ">
        <div class="flex items-center gap-3">
          <img class="h-10 rounded-full" src="./assets/User_Avatar.svg" alt="">
          <div>
            <p class="font-semibold text-indigo-700 dark:text-white transition-colors duration-1000 ">Sarah Andrews</p>
            <p class="font-light">$100k in revenue</p>
          </div>
        </div>
        <p class="w-[95%]">Setting up my portfolio with Fiber took no more than 10 minutes. Since then, my portfolio has attracted a lot of clients and made me more than $100k.</p>
        <button class="bg-transparent text-indigo-700 font-semibold border-slate-300 dark:border-slate-400 dark:text-white hover:scale-105 transition-colors duration-1000 ">View Sarah's Portfolio</button>
      </div>
      <div class="flex flex-col gap-4 text-left border border-slate-300 dark:border-none dark:bg-indigo-500 rounded p-5 mb-10 lg:mb-0 transition-colors duration-1000 ">
        <div class="flex items-center gap-3">
          <img class="h-10 rounded-full" src="./assets/User_Avatar_2.svg" alt="">
          <div>
            <p class="font-semibold text-indigo-700 dark:text-white transition-colors duration-1000 ">Mathew Higgins</p>
            <p class="font-light">$20k in revenue</p>
          </div>
        </div>
        <p class="w-[95%]">I have been getting A LOT of leads ever since I used Fiber's premade templates, now I just need to work on my case studies and I'll be ready to go!</p>
        <button class="bg-transparent text-indigo-700 font-semibold border-slate-300 dark:border-slate-400 dark:text-white hover:scale-105 transition-colors duration-1000 ">View Mathew's Portfolio</button>
      </div>
      <div class="flex flex-col gap-4 text-left border border-slate-300 dark:border-none dark:bg-indigo-500 rounded p-5 transition-colors duration-1000 ">
        <div class="flex items-center gap-3">
          <img class="h-10 rounded-full" src="./assets/User_Avatar_32.svg" alt="">
          <div>
            <p class="font-semibold text-indigo-700 dark:text-white transition-colors duration-1000 ">Janice Dave</p>
            <p class="font-light">$30k in revenue</p>
          </div>
        </div>
        <p class="w-[91%]">I only just stated freelancing this year and I have already made more than I ever made in my full-time job. The templates are just so amazing.</p>
        <button class="bg-transparent text-indigo-700 font-semibold border-slate-300 dark:border-slate-400 dark:text-white hover:scale-105 transition-colors duration-1000 ">View Janice's Portfolio</button>
      </div>
    </section>
  </main>
  <footer class="px-8 py-16 sm:px-16 2xl:px-80 flex flex-col lg:flex-row justify-between gap-8">
    <div class="flex flex-col text-left gap-2">
      <strong>Fiber</strong>
      <p class="max-w-sm">With Fiber, you can setup your own personal portfolio in minutes with dozens of premade, beautiful templates.</p>
      <p>Made with ♥ in Cambodia.</p>
    </div>
    <div class="flex flex-col text-left gap-4">
      <strong>Sitemap</strong>
      <ul class="flex flex-col gap-2">
        <li>
          <a href="#">Homepage</a>
        </li>
        <li>
          <a href="#">Pricing</a>
        </li>
        <li>
          <a href="#">Testimonials</a>
        </li>
        <li>
          <a href="#">Features</a>
        </li>
      </ul>
    </div>
    <div class="flex flex-col text-left gap-4">
      <strong>Resources</strong>
      <ul class="flex flex-col gap-2">
        <li>
          <a href="#">Support</a>
        </li>
        <li>
          <a href="#">Contact</a>
        </li>
        <li>
          <a href="#">FAQ</a>
        </li>
      </ul>
    </div>
    <div class="flex flex-col text-left gap-4">
      <strong>Company</strong>
      <ul class="flex flex-col gap-2">
        <li>
          <a href="#">About</a>
        </li>
        <li>
          <a href="#">Customers</a>
        </li>
        <li>
          <a href="#">Blog</a>
        </li>
      </ul>
    </div>
    <div class="flex flex-col text-left gap-4">
      <strong>Portfolios</strong>
      <ul class="flex flex-col gap-2">
        <li>
          <a href="#">Sarah Andrews</a>
        </li>
        <li>
          <a href="#">Mathew Higgins</a>
        </li>
        <li>
          <a href="#">Janice Dave</a>
        </li>
      </ul>
    </div>
  </footer>
</template>
<style lang="postcss">
#mobile-nav > ul > li:hover, #mobile-nav > ul > li:active {
  @apply text-indigo-700 transition-colors duration-500;
}
.main-text {
  @apply text-indigo-700 dark:text-indigo-500 transition-colors duration-1000 ;
}
.heading {
  @apply text-left text-4xl font-semibold leading-[3rem];
}
footer > div > ul > li > a {
  @apply font-light;
}
.main-bg {
  @apply bg-indigo-700 dark:bg-indigo-500 transition-colors duration-1000;
}
</style>
<script setup>
import { onMounted } from 'vue';
const toggleNav = () => {
  const nav = document.querySelector('#mobile-nav');
  console.log(nav.style.opacity);
  if (nav.style.opacity == 0) {
    nav.style.opacity = 1
    nav.style.height = 'auto'
  } else {
    nav.style.opacity = 0
    nav.style.height = 0
  }
}
const goToAuth = () => {
  window.location.href = '/fiber/auth/'
}
const toggleDark = () => {
  const darkIcon = document.querySelector('#dark-icon');
  const lightIcon = document.querySelector('#light-icon');
  darkIcon.classList.toggle('hidden')
  lightIcon.classList.toggle('hidden')
  if (localStorage.getItem('theme')) {
      if (localStorage.getItem('theme') === 'light') {
          document.documentElement.classList.add('dark');
          localStorage.setItem('theme', 'dark');
      } else {
          document.documentElement.classList.remove('dark');
          localStorage.setItem('theme', 'light');
      }
  } else {
      if (document.documentElement.classList.contains('dark')) {
          document.documentElement.classList.remove('dark');
          localStorage.setItem('theme', 'light');
      } else {
          document.documentElement.classList.add('dark');
          localStorage.setItem('theme', 'dark');
      }
  }
}
onMounted(() => {
  const darkIcon = document.querySelector('#dark-icon');
  const lightIcon = document.querySelector('#light-icon');
  if (localStorage.getItem('theme') === 'dark' || (!('theme' in localStorage) && window.matchMedia('(prefers-color-scheme: dark)').matches)) {
    document.documentElement.classList.add('dark');
    lightIcon.classList.remove('hidden');
  } else {
    darkIcon.classList.remove('hidden');
    document.documentElement.classList.remove('dark')
  }
})
</script>