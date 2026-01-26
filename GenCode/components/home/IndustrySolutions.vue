<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
import Card from './Card.vue'

const fullText = 'Conoce los sectores en los que hemos operado'
const animatedText = ref('')
const animatedStarted = ref(false)
const animatedTextRef = ref(null)

function typeWriter(text, i = 0) {
  if (i <= text.length) {
    animatedText.value = text.slice(0, i)
    setTimeout(() => typeWriter(text, i + 1), 50)
  }
}

function handleIntersection(entries) {
  if (entries[0].isIntersecting && !animatedStarted.value) {
    animatedStarted.value = true
    typeWriter(fullText)
  }
}

onMounted(() => {
  if (animatedTextRef.value) {
    const observer = new window.IntersectionObserver(handleIntersection, { threshold: 0.5 })
    observer.observe(animatedTextRef.value)
  }
  updateCardsPerView()
  window.addEventListener('resize', updateCardsPerView)
})

onUnmounted(() => {
  window.removeEventListener('resize', updateCardsPerView)
})

const cards = [
  {
    image: '/images/HomePage/Sectores/imageAlimenticia.png',
    title: 'Alimenticio',
    text: 'Una web única para compartir el mensaje de cervecería mexican',
    ruta: '/'
  },
  {
    image: '/images/HomePage/Sectores/imageAgricola.png',
    title: 'Agrícola',
    text: 'Soluciones personalizadas para pizca, recolección y empaque',
    ruta: '/'
  },
  {
    image: '/images/HomePage/Sectores/imageInmobiliaria.png',
    title: 'Inmobiliario',
    text: 'Sistema de control de nómina y páginas web para conversión',
    ruta: '/'
  },
  {
    image: '/images/HomePage/Sectores/imageIndustrial.png',
    title: 'Industrial',
    text: 'Sistema de trazabilidad para gestión de reparaciones industriales',
    ruta: '/'
  },
  {
    image: '/images/HomePage/Sectores/imageInmobiliaria.png',
    title: 'Inmobiliario',
    text: 'Sistema de control de nómina y páginas web para conversión',
    ruta: '/'
  },
  {
    image: '/images/HomePage/Sectores/imageIndustrial.png',
    title: 'Industrial',
    text: 'Sistema de trazabilidad para gestión de reparaciones industriales',
    ruta: '/'
  }
]

const carouselIndex = ref(0)
const cardsPerView = ref(4)

function updateCardsPerView() {
  if (typeof window !== 'undefined') {
    if (window.innerWidth < 640) {
      cardsPerView.value = 1
    } else if (window.innerWidth < 768) {
      cardsPerView.value = 2
    } else if (window.innerWidth < 1024) {
      cardsPerView.value = 3
    } else {
      cardsPerView.value = 4
    }
   
    if (carouselIndex.value + cardsPerView.value > cards.length) {
      carouselIndex.value = Math.max(0, cards.length - cardsPerView.value)
    }
  }
}

const visibleCards = computed(() => cards.slice(carouselIndex.value, carouselIndex.value + cardsPerView.value))
const maxIndex = computed(() => Math.max(0, cards.length - cardsPerView.value))

function nextSlide() {
  if (carouselIndex.value < maxIndex.value) {
    carouselIndex.value++
  }
}
function prevSlide() {
  if (carouselIndex.value > 0) {
    carouselIndex.value--
  }
}

const totalDots = computed(() => Math.ceil(cards.length / cardsPerView.value))
const currentDot = computed(() => Math.floor(carouselIndex.value / cardsPerView.value))
</script>

<template>
  <section class="bg-fondo-gray w-full py-12 sm:py-16 lg:py-20">
  
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <p 
        ref="animatedTextRef" 
        class="font-bold bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent
          text-2xl sm:text-3xl md:text-5xl lg:text-6xl max-w-4xl"
      >
        {{ animatedText }}
      </p>

      <p  data-aos="fade-up" data-aos-delay="900" data-aos-duration="800" class="text-[#C7C8CA] mt-4 sm:mt-6 text-sm sm:text-base max-w-2xl">
        Contamos con amplia experiencia en diferentes sectores como, alimenticio, agrícola, inmobiliario, moda, arte, entre otros
      </p>
    </div>

   
    <div   class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mt-8 sm:mt-12">
     
      <button
        class="absolute left-0 sm:left-2 top-1/2 -translate-y-1/2 z-20 bg-[#222]/90 backdrop-blur-sm text-white rounded-full 
          w-8 h-8 sm:w-10 sm:h-10 flex items-center justify-center shadow-lg shadow-black/50 
          transition-all duration-300 hover:bg-primary hover:shadow-[0_0_15px_rgba(0,145,255,0.4)]
          disabled:opacity-30 disabled:hover:bg-[#222]/90 disabled:hover:shadow-black/50"
        @click="prevSlide" 
        :disabled="carouselIndex === 0"
        aria-label="Anterior"
      >
        <svg class="w-4 h-4 sm:w-5 sm:h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
        </svg>
      </button>

    
      <div  data-aos="fade-up" data-aos-delay="1000" data-aos-duration="800" class="overflow-hidden mx-8 sm:mx-12">
        <div 
          class="grid gap-4 sm:gap-6 py-4 transition-all duration-500"
          :class="{
            'grid-cols-1': cardsPerView === 1,
            'grid-cols-2': cardsPerView === 2,
            'grid-cols-3': cardsPerView === 3,
            'grid-cols-4': cardsPerView === 4
          }"
        >
          <Card
            v-for="(card, i) in visibleCards"
            :key="carouselIndex + '-' + i + '-' + card.title"
            :image="card.image"
            :title="card.title"
            :text="card.text"
            :ruta="card.ruta"
            class="w-full"
          />
        </div>
      </div>

      <button
        class="absolute right-0 sm:right-2 top-1/2 -translate-y-1/2 z-20 bg-[#222]/90 backdrop-blur-sm text-white rounded-full 
          w-8 h-8 sm:w-10 sm:h-10 flex items-center justify-center shadow-lg shadow-black/50 
          transition-all duration-300 hover:bg-primary hover:shadow-[0_0_15px_rgba(0,145,255,0.4)]
          disabled:opacity-30 disabled:hover:bg-[#222]/90 disabled:hover:shadow-black/50"
        @click="nextSlide" 
        :disabled="carouselIndex >= maxIndex"
        aria-label="Siguiente"
      >
        <svg class="w-4 h-4 sm:w-5 sm:h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
        </svg>
      </button>

    <!-- Mobile -->
      <div  data-aos="fade-up" data-aos-delay="900" data-aos-duration="800" class="flex justify-center gap-2 mt-4 sm:hidden">
        <button
          v-for="dot in totalDots"
          :key="dot"
          @click="carouselIndex = (dot - 1) * cardsPerView"
          class="w-2 h-2 rounded-full transition-all duration-300"
          :class="currentDot === dot - 1 
            ? 'bg-[#0091FF] w-6 shadow-[0_0_10px_rgba(0,145,255,0.5)]' 
            : 'bg-white/30 hover:bg-white/50'"
          :aria-label="`Ir a página ${dot}`"
        />
      </div>
    </div>

    
    <div  data-aos="fade-up" data-aos-delay="1000" data-aos-duration="800" class="flex justify-center items-center mt-16 sm:mt-20 px-4">
      <p class="tracking-wider text-center font-bold bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent
        text-3xl sm:text-5xl md:text-6xl lg:text-7xl max-w-4xl">
        Nuestros servicios
        <span class="block">principales</span>
      </p>
    </div>
  </section>
</template>