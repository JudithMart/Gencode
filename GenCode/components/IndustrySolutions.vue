

<script setup>
import { ref, computed, onMounted } from 'vue'

const fullText = 'Conoce los sectores en los  que hemos operado'
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
const visibleCards = computed(() => cards.slice(carouselIndex.value, carouselIndex.value + 4))

function nextSlide() {
    if (carouselIndex.value + 4 < cards.length) {
        carouselIndex.value++
    }
}
function prevSlide() {
    if (carouselIndex.value > 0) {
        carouselIndex.value--
    }
}
</script>
<template>
    <section class="bg-[#161616] w-full py-20">
        <div class="max-w-7xl mx-auto px-6 sm:px-10 lg:px-[5cm]">
                <p ref="animatedTextRef" class="font-bold bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent
                    text-3xl sm:text-4xl md:text-6xl max-w-4xl whitespace-pre-line">
                    {{ animatedText }}
                </p>

            <p class="text-[#C7C8CA] mt-6 text-base max-w-2xl whitespace-pre-line">
             Contamos con amplia experiencia en diferentes sectores como, alimenticio, agrícola, inmobiliario, moda, arte, entre otros
            </p>
        </div>

        <div class="relative overflow-hidden max-w-[64rem] mx-auto">
            <button
                class="absolute left-2 top-1/2 -translate-y-1/2 z-20 bg-[#222] text-white rounded-full w-10 h-10 flex items-center justify-center shadow-lg shadow-black disabled:opacity-30"
                @click="prevSlide" :disabled="carouselIndex === 0"
                aria-label="Anterior"
            >
                <span class="text-2xl">&#8592;</span>
            </button>
            <div class="flex gap-6 py-6 transition-transform duration-500">
                <Card
                  v-for="(card, i) in visibleCards"
                  :key="i + '-' + card.title"
                  :image="card.image"
                  :title="card.title"
                  :text="card.text"
                  :ruta="card.ruta"
                />
            </div>
            <button
                class="absolute right-2 top-1/2 -translate-y-1/2 z-20 bg-[#222] text-white rounded-full w-10 h-10 flex items-center justify-center shadow-lg shadow-black disabled:opacity-30"
                @click="nextSlide" :disabled="carouselIndex + 4 >= cards.length"
                aria-label="Siguiente"
            >
                <span class="text-2xl">&#8594;</span>
            </button>
        </div>
        <div class=" flex justify-center items-center mt-20 ">
           <p  class="tracking-wider text-center font-bold bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent
                    text-4xl sm:text-6xl md:text-7xl max-w-4xl whitespace-pre-line">
             Nuestros servicios
             <span class="block"> principales</span>
            </p>
        </div>

    </section>
</template>
