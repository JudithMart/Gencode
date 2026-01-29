<template>
  <div>
    <Header />
    <NuxtPage />
    <!-- BOTÓN FLOTANTE -->
    <div class="fixed bottom-4 left-0 right-0 flex justify-center z-50 px-4">
      <button :class=" [
        'px-5 py-2.5 text-sm font-medium rounded-full shadow-md',
        'transition-all duration-300 ease-out',
        'hover:shadow-xl hover:-translate-y-0.5 hover:scale-105',
        'active:scale-95',
        'focus:outline-none focus:ring-0 focus:ring-offset-0',
        'animate-float-soft',
        isInSpecialSection
          ? 'bg-primary text-white border-primary hover:bg-transparent border-2 '
          : 'bg-transparent text-gray-300 border-2 border-primary  hover:bg-primary'
      ]">
        Contáctanos
      </button>
    </div>
  </div>

</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isInSpecialSection = ref(true)

let scrollTimeout = null

const handleScroll = () => {
  // Detectar hero-section
  const hero = document.querySelector('.hero-section')
  const industry = document.querySelector('.empSystem-section')
  const scrollY = window.scrollY
  let inHero = false
  let inIndustry = false

  if (hero) {
    const heroHeight = hero.offsetHeight
    inHero = scrollY < heroHeight - 100
  }

  if (industry) {
    const rect = industry.getBoundingClientRect()
    const top = rect.top + window.scrollY
    const bottom = rect.bottom + window.scrollY
    inIndustry = scrollY + window.innerHeight > top + 100 && scrollY < bottom - 100
  }

  isInSpecialSection.value = inHero || inIndustry
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  clearTimeout(scrollTimeout)
})
</script>

<style scoped>
@keyframes float-soft {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-4px);
  }
}
.animate-float-soft {
  animation: float-soft 2.8s ease-in-out infinite;
}
</style>
