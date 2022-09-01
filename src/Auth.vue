<template>
    <button @click="toggleDark"
        class="fixed h-15 w-15 bottom-8 right-8 bg-teal-700 dark:bg-teal-600 transition-colors duration-1000 text-white p-2 rounded-full hover:bg-teal-800">
        <svg id="light-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
            stroke="currentColor" class="w-6 h-6 hidden">
            <path stroke-linecap="round" stroke-linejoin="round"
                d="M12 3v2.25m6.364.386l-1.591 1.591M21 12h-2.25m-.386 6.364l-1.591-1.591M12 18.75V21m-4.773-4.227l-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 11-7.5 0 3.75 3.75 0 017.5 0z" />
        </svg>
        <svg id="dark-icon" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
            stroke="currentColor" class="w-6 h-6 hidden">
            <path stroke-linecap="round" stroke-linejoin="round"
                d="M21.752 15.002A9.718 9.718 0 0118 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 003 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 009.002-5.998z" />
        </svg>
    </button>
    <div class="grid lg:grid-cols-2 min-h-full">
        <div class="grid gap-4 text-left p-10 sm:py-4 sm:px-16 lg:px-20 2xl:px-40">
            <a href="/" class="text-2xl font-extrabold">Fiber</a>
            <h1 class="mt-8 mb-2 text-left text-4xl font-semibold leading-[3rem];">Create your Fiber account</h1>
            <div class="input-container">
                <label for="name">Your Name</label>
                <input type="text" placeholder="John Doe">
            </div>
            <div class="input-container">
                <label for="email">Email</label>
                <input type="email" placeholder="john@example.com">
            </div>
            <div class="input-container">
                <label for="password">Password</label>
                <div class="w-full flex relative">
                    <input class="w-full" type="password" placeholder="At least 8 characters">
                    <img class="absolute right-4 top-1/2 -translate-y-1/2" src="/src/assets/hide_password.svg" alt="">
                </div>
            </div>
            <div class="flex items-start gap-2">
                <input type="checkbox" name="terms">
                <p class="max-w-[30ch] lg:max-w-sm">By creating an account on Fiber, you agree to the <a href="#" class="text-indigo-700 underline">Terms & Conditions.</a></p>
            </div>
            <button class="main-bg text-white max-h-14">Create Fiber Account</button>
            <p class="text-center">Already have an account? <a href="/" class="text-indigo-700 underline">Sign In</a></p>
        </div>
        <div class="hidden lg:flex lg:flex-col place-content-center main-bg  p-20 2xl:p-40 gap-4">
            <div>
                <img src="/src/assets/Sign_Up_Image.png" alt="">
            </div>
            <h1 class="mt-8 mb-2 text-white text-4xl font-semibold leading-[3rem];">Unparalleled Templates</h1>
            <p class="text-white">Crafted by a team of professional designers, our templates are unparalleled in the market.</p>
            <ul class="flex justify-center gap-2">
                <li class="h-2.5 w-2.5 rounded-full bg-white"></li>
                <li class="h-2.5 w-2.5 rounded-full bg-indigo-400"></li>
                <li class="h-2.5 w-2.5 rounded-full bg-indigo-400"></li>
                <li class="h-2.5 w-2.5 rounded-full bg-indigo-400"></li>
            </ul>
        </div>
    </div>
</template>
<style lang="postcss">
.input-container {
    @apply flex flex-col gap-1;
}
label {
    @apply font-semibold;
}
input {
    @apply border border-zinc-300 rounded p-3;
}
.main-bg {
    @apply bg-indigo-700 dark:bg-indigo-500 transition-colors duration-1000;
}
</style>
<script setup>
import { onMounted } from 'vue';
const toggleNav = () => {
    const nav = document.querySelector('#mobile-nav');
    if (nav.style.display == 'none') {
        nav.style.display = ''
    } else {
        nav.style.display = 'none'
    }
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