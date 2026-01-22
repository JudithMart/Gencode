
<template>
  <section class="bg-fondo-gray w-full py-12 sm:py-16 lg:py-20 -mt-px">

    <div class="flex justify-center items-center px-4">
      <p class="font-bold bg-gradient-to-b text-center from-text-fromGray to-text-toGray bg-clip-text text-transparent
        text-3xl sm:text-4xl md:text-6xl lg:text-7xl max-w-4xl">
        Las mejores empresas
        <span class="block">confían en nosotros</span>
      </p>
    </div>
 
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 mt-10 sm:mt-14 ">
      <div class="flex flex-wrap justify-center gap-6 sm:gap-10 lg:gap-14">
        <CardTrustedBy
          v-for="empresa in empresas"
          :key="empresa.title"
          :image="empresa.image"
          :title="empresa.title"
          :description="empresa.description"
          :link="empresa.link"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import CardTrustedBy from './CardTrustedBy.vue';

const empresas = [
  {
    image: '/images/HomePage/Images/TrustedBy/imageBru.png',
    title: 'Bru',
    description: 'Trabajar con GENCODE ha sido una gran experiencia. Son un equipo profesional, proactivo y creativo, con una capacidad de ejecución sobresaliente. Desde el inicio entendieron perfectamente nuestras necesidades y aportaron soluciones ágiles y efectivas. Además, sus precios son muy justos para el nivel de calidad y compromiso que ofrecen.  Sin duda, una colaboración que recomiendo ampliamente'
    
  },
  {
    image: '/images/HomePage/Images/TrustedBy/imageCitelis.png',
    title: 'Citelis',
    description: 'Trabajar con GENCODE ha sido una gran experiencia. Son un equipo profesional, proactivo y creativo, con una capacidad de ejecución sobresaliente. Desde el inicio entendieron perfectamente nuestras necesidades y aportaron soluciones ágiles y efectivas. Además, sus precios son muy justos para el nivel de calidad y compromiso que ofrecen.  Sin duda, una colaboración que recomiendo ampliamente'
    
  },
  {
    image: '/images/HomePage/Images/TrustedBy/imageNge.png',
    title: 'Inmobiliaria Premium',
    description: 'Trabajar con GENCODE ha sido una gran experiencia. Son un equipo profesional, proactivo y creativo, con una capacidad de ejecución sobresaliente. Desde el inicio entendieron perfectamente nuestras necesidades y aportaron soluciones ágiles y efectivas. Además, sus precios son muy justos para el nivel de calidad y compromiso que ofrecen.  Sin duda, una colaboración que recomiendo ampliamente'
    
  },
  
]
</script>