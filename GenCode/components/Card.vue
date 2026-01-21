<template>
    <div class="relative flex flex-col justify-center items-center 
    transition duration-300 hover:scale-105  ">
        <NuxtImg :src="image" :alt="title" class="rounded-lg w-60 h-80 object-cover shadow-lg shadow-black" format="webp" quality="80" />
        <div class="absolute top-0 left-0 w-full h-full bg-black bg-opacity-40 rounded-lg z-10"></div>
                <div class="absolute left-2 bottom-6 z-20 w-full">
                        <p class="text-white font-semibold">{{ title }}</p>
                        <p class="mr-3 text-white text-[11px]">{{ text }}</p>
                        
                </div>
                <NuxtLink :to="ruta"
                    class="absolute bottom-2 right-2 z-30 overflow-hidden bg-[#333337] rounded-full w-6 h-6 flex items-center justify-center
                    text-white transition-all duration-300 [transition-timing-function:cubic-bezier(0.175,0.885,0.32,1.275)] active:-translate-y-1 
                    active:scale-x-90 active:scale-y-110 mt-2 shadow-lg shadow-black "
                >
                    <span class="text-lg">+</span>
                </NuxtLink>
        
    </div>
</template>

<script setup>
defineProps({
    image: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    text: {
        type: String,
        required: true
    },
      ruta: {
        type: String,
        required: true
    }
})
</script>