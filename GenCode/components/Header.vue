<template>
  <header 
    class="fixed top-0 left-0 w-full z-50 bg-black/ backdrop-blur-sm border-b border-transparent transition-all duration-300"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-14 md:h-16">
        <!-- Logo -->
        <NuxtLink to="/" class="flex-shrink-0 group">
          <NuxtImg 
            src="/images/logo.png" 
            alt="Logo" 
            class="object-contain w-24 md:w-32 transition-all duration-300 group-hover:brightness-125 group-hover:drop-shadow-[0_0_8px_rgba(255,255,255,0.3)]" 
            format="webp" 
          />
        </NuxtLink>

        <!-- Desktop Nav -->
        <nav class="hidden md:flex items-center gap-10 " aria-label="Navegación principal">
          <NuxtLink 
            v-for="link in navLinks" 
            :key="link.label"
            :to="link.to" 
            class="group relative text-sm font-medium text-white/60 transition-all duration-300 hover:text-white "
          >
            <span class="relative z-10 transition-all duration-300 group-hover:drop-shadow-[0_0_8px_rgba(255,255,255,0.4)]">
              {{ link.label }}
            </span>
          
            <span class="absolute -bottom-1 left-0 w-full h-[2px] bg-primary rounded-full scale-x-0 transition-all duration-300 group-hover:scale-x-100"></span>
            
            <span class="absolute -bottom-1 left-0 w-full h-[2px] bg-primary rounded-full blur-[4px] scale-x-0 opacity-0 transition-all duration-300 group-hover:scale-x-100 group-hover:opacity-100"></span>
         
            <span class="absolute -bottom-2 left-1/2 -translate-x-1/2 w-3/4 h-[6px] bg-primary/60 rounded-full blur-[8px] 
                        scale-x-0 opacity-0 transition-all duration-300 group-hover:scale-x-100 group-hover:opacity-80"></span>
          </NuxtLink>
        </nav>

        <!-- CTA Button Desktop -->
        <div class="hidden md:block flex-shrink-0">
          <FillButton class="text-sm px-5 py-2 rounded-full transition-all duration-300 hover:shadow-[0_0_20px_rgba(0,145,255,0.5)] hover:brightness-110">
            Contáctanos
          </FillButton>
        </div>

        <!-- Hamburger Icon -->
        <button 
          @click="toggleMenu" 
          class="md:hidden relative flex flex-col justify-center items-center w-10 h-10 rounded-lg transition-all duration-300 hover:bg-white/10 focus:outline-none focus-visible:ring-2 focus-visible:ring-[#0091FF]"
          :aria-expanded="isOpen"
          aria-controls="mobile-menu"
          aria-label="Abrir menú de navegación"
        >
          <span 
            :class="[
              'block w-5 h-[1.5px] bg-white rounded-full transition-all duration-300 ease-out',
              isOpen ? 'rotate-45 translate-y-[5px] shadow-[0_0_8px_rgba(255,255,255,0.6)]' : ''
            ]"
          ></span>
          <span 
            :class="[
              'block w-5 h-[1.5px] bg-white rounded-full transition-all duration-300 ease-out mt-[5px]',
              isOpen ? 'opacity-0 scale-0' : ''
            ]"
          ></span>
          <span 
            :class="[
              'block w-5 h-[1.5px] bg-white rounded-full transition-all duration-300 ease-out mt-[5px]',
              isOpen ? '-rotate-45 -translate-y-[7px] shadow-[0_0_8px_rgba(255,255,255,0.6)]' : ''
            ]"
          ></span>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <Transition
      enter-active-class="transition-all duration-300 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <nav 
        v-if="isOpen" 
        id="mobile-menu"
        class="md:hidden absolute top-full left-0 w-full bg-black/85 backdrop-blur-md border-b border-white/5"
        aria-label="Menú móvil"
      >
        <div class="max-w-7xl mx-auto px-4 py-4 flex flex-col gap-1">
          <NuxtLink 
            v-for="link in navLinks" 
            :key="link.label"
            @click="closeMenu"
            :to="link.to" 
            class="group relative block px-4 py-3 text-base font-medium text-white/60 rounded-lg transition-all duration-300 hover:text-white hover:bg-white/5 hover:shadow-[inset_0_0_20px_rgba(255,255,255,0.05)]"
          >
            <span class="relative z-10 transition-all duration-300 group-hover:drop-shadow-[0_0_10px_rgba(255,255,255,0.4)]">
              {{ link.label }}
            </span>
            <span class="absolute left-0 top-1/2 -translate-y-1/2 w-0.5 h-0 bg-primary rounded-full transition-all duration-300 group-hover:h-1/2 group-hover:shadow-[0_0_10px_rgba(0,145,255,0.6)]"></span>
          </NuxtLink>
          <div class="mt-3 px-4">
            <FillButton @click="closeMenu" class="w-full py-2.5 rounded-full transition-all duration-300 hover:shadow-[0_0_25px_rgba(0,145,255,0.4)]">
              Contáctanos
            </FillButton>
          </div>
        </div>
      </nav>
    </Transition>
  </header>
  

 
</template>

<script setup>
import { ref } from 'vue'
import FillButton from './home/FillButton.vue'

const isOpen = ref(false)

const navLinks = [
  { label: 'Nosotros', to: '/' },
  { label: 'Servicios', to: '/' },
  { label: 'Portafolio', to: '/' },
  { label: 'Reseñas', to: '/' },
  { label: 'Devs', to: '/' },
]

const toggleMenu = () => {
  isOpen.value = !isOpen.value
}

const closeMenu = () => {
  isOpen.value = false
}
</script>