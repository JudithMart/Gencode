<template>
  <div class="relative flex flex-col justify-center items-center transition duration-300 hover:scale-105 group">
    <NuxtImg 
      :src="image" 
      :alt="title" 
      class="rounded-xl w-full aspect-[3/4] object-cover shadow-lg shadow-black/50" 
      format="webp" 
      quality="80" 
    />
    <!-- Overlay con gradiente más elegante -->
    <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/20 to-transparent rounded-xl z-10"></div>
    
    <!-- Contenido -->
    <div class="absolute left-3 right-3 bottom-12 sm:bottom-10 z-20">
      <p class="text-white font-semibold text-sm sm:text-base">{{ title }}</p>
      <p class="text-white/70 text-[11px] sm:text-xs mt-1 line-clamp-2">{{ text }}</p>
    </div>
    
    <!-- Botón + con hover glow -->
    <NuxtLink 
      :to="ruta"
      class="absolute bottom-3 right-3 z-30 bg-[#333337] rounded-full w-7 h-7 sm:w-8 sm:h-8 flex items-center justify-center
        text-white transition-all duration-300 hover:bg-[#0091FF] hover:shadow-[0_0_15px_rgba(0,145,255,0.5)]
        active:-translate-y-1 active:scale-90 shadow-lg shadow-black/50"
    >
      <span class="text-lg sm:text-xl leading-none">+</span>
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