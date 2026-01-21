<template>
    <div class="fixed top-0 left-0 w-full z-50 bg-transparent flex items-center justify-between p-4">
        <NuxtImg src="/images/logo.png" alt="Logo" class="object-contain min-w-[80px] w-24 md:w-32" format="webp" />

        <!-- Desktop Nav -->
        <nav class="hidden md:flex items-center flex-1 justify-center">
            <NuxtLink to="/" class="mr-4 text-xs font-light  text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">Nosotros</NuxtLink>
            <NuxtLink to="/" class="mr-4 text-xs font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">Servicios</NuxtLink>
            <NuxtLink to="/" class="mr-4 text-xs font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">Portafolio</NuxtLink>
            <NuxtLink to="/" class="mr-4 text-xs font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">Reseñas</NuxtLink>
            <NuxtLink to="/" class="mr-4 text-xs font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">Devs</NuxtLink>
        </nav>

        <div class="hidden md:block">
            <FillButton class="text-sm">Contáctanos</FillButton>
        </div>

        <!-- Hamburger Icon -->
        <button @click="isOpen = !isOpen" class="md:hidden flex flex-col justify-center items-center w-10 h-10 focus:outline-none">
            <span :class="[isOpen ? 'rotate-45 translate-y-2' : '', 'block w-8 h-1 bg-white mb-1 transition-all duration-300']"></span>
            <span :class="[isOpen ? 'opacity-0' : '', 'block w-8 h-1 bg-white mb-1 transition-all duration-300']"></span>
            <span :class="[isOpen ? '-rotate-45 -translate-y-2' : '', 'block w-8 h-1 bg-white transition-all duration-300']"></span>
        </button>

        <!-- Mobile Menu -->
        <transition name="fade">
            <div v-if="isOpen" @click.self="isOpen = false" class="fixed inset-0 bg-black bg-opacity-80 flex flex-col items-center justify-center md:hidden z-50">
                <button @click="isOpen = false" class="absolute top-6 right-6 text-white text-4xl font-bold focus:outline-none">×</button>
                <NuxtLink @click="isOpen = false" to="/" class="mb-6 text-2xl font-light text-white hover:underline hover:decoration-[#0091FF]">Nosotros</NuxtLink>
                <NuxtLink @click="isOpen = false" to="/" class="mb-6 text-2xl font-light text-white hover:underline hover:decoration-[#0091FF]">Servicios</NuxtLink>
                <NuxtLink @click="isOpen = false" to="/" class="mb-6 text-2xl font-light text-white hover:underline hover:decoration-[#0091FF]">Portafolio</NuxtLink>
                <NuxtLink @click="isOpen = false" to="/" class="mb-6 text-2xl font-light text-white hover:underline hover:decoration-[#0091FF]">Reseñas</NuxtLink>
                <NuxtLink @click="isOpen = false" to="/" class="mb-8 text-2xl font-light text-white hover:underline hover:decoration-[#0091FF]">Devs</NuxtLink>
                <FillButton  @click="isOpen = false">Contáctanos</FillButton>
            </div>
        </transition>
    </div>
</template>

<script setup>
import { ref } from 'vue'
const isOpen = ref(false)
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
    transition: opacity 0.3s;
}
.fade-enter-from, .fade-leave-to {
    opacity: 0;
}
</style>