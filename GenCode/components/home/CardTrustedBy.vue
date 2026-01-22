<template>
    <div class="group relative cursor-pointer" @mouseenter="isExpanded = true" @mouseleave="isExpanded = false"
        @click="toggleExpand">

        <div class="relative overflow-hidden rounded-xl bg-[#1a1a1d] border border-white/5 
        transition-all duration-500 ease-out 
        h-96 sm:h-[28rem] w-80 " :class="isExpanded ? 'shadow-[0_0_30px_rgba(0,145,255,0.15)]' : 'shadow-lg shadow-black/30'">

            <div class="absolute inset-0 w-full h-full transition-all duration-500"
                :class="isExpanded ? 'opacity-20 scale-110' : 'opacity-100 scale-100'">
                <NuxtImg :src="image" :alt="title"
                    class="w-full h-full object-cover filter brightness-90" format="webp" />
            </div>


            <div class="absolute inset-0 flex flex-col justify-center p-5 sm:p-6 transition-all duration-500" :class="isExpanded
                ? 'opacity-100 translate-y-0'
                : 'opacity-0 translate-y-4 pointer-events-none'">
                <h3
                    class="text-white font-semibold text-lg sm:text-xl mb-2 drop-shadow-[0_0_10px_rgba(255,255,255,0.2)]">
                    {{ title }}
                </h3>
                <p class="text-white/70 text-sm sm:text-base leading-relaxed line-clamp-3">
                    {{ description }}
                </p>


            </div>


            <div class="absolute inset-0 rounded-xl border-2 border-primary/0 transition-all duration-500 pointer-events-none"
                :class="isExpanded ? 'border-primary/40' : ''"></div>


            <div class="absolute -bottom-2 left-1/2 -translate-x-1/2 w-1/2 h-4 bg-primborder-primary/40 blur-xl transition-all duration-500"
                :class="isExpanded ? 'opacity-100' : 'opacity-0'"></div>
        </div>


        <div class="absolute top-3 right-3 w-6 h-6 rounded-full bg-white/10 flex items-center justify-center 
        transition-all duration-300 sm:opacity-0" :class="isExpanded ? 'rotate-45' : ''">
            <span class="text-white/60 text-sm">+</span>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
    image: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    description: {
        type: String,
        required: true
    },

})

const isExpanded = ref(false)

const toggleExpand = () => {

    if (window.innerWidth < 640) {
        isExpanded.value = !isExpanded.value
    }
}
</script>