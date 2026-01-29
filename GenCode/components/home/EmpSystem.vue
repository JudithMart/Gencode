<script setup lang="ts">
import EmptyButton from './EmptyButton.vue';
import FillButton from './FillButton.vue';

</script>

<template>
    <section class=" empSystem-section relative w-full overflow-hidden
            min-h-fit lg:min-h-[95vh]
            flex flex-col pt-10 -mt-px">

        <!-- Fondo DESKTOP -->
        <NuxtImg src="/images/HomePage/Fondos/EmpSystem/Desktop.jpg" alt="Mokup servicios" class="absolute inset-0 w-full h-full object-cover -z-10
             hidden lg:block" format="webp" quality="80" fill />


        <!-- Fondo LAPTOP -->
        <NuxtImg src="/images/HomePage/Fondos/EmpSystem/Laptop.jpg" alt="Servicios web" class="absolute inset-0 w-full h-full object-cover -z-10
             hidden sm:block lg:hidden" format="webp" quality="80" fill />

        <!-- Fondo MOBILE -->
        <NuxtImg src="/images/HomePage/Fondos/EmpSystem/Mobile.png"
            class="absolute inset-0 w-full h-full object-cover block md:hidden -z-10" alt="Fondo mobile" format="webp"
            quality="80" />

        <div  data-aos="fade-up" data-aos-delay="900" data-aos-duration="800" class="flex items-center flex-col px-2 z-10">
            <p class="pb-2  font-normal text-center  bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent
                 text-5xl sm:text-5xl md:text-7xl lg:text-7xl 2xl:text-7xl max-w-5xl leading-tight whitespace-pre-line ">

                Sistemas empresariales
            </p>
            <p class="mt-3 px-5 text-[#FFFFFF] text-center  text-xs
                   sm:text-sm 
                   md:text-xl max-w-2xl tracking-wider  ">Soluciones personalizadas
                para
                tu empresa cuando un CRM no es lo que necesitas.</p>
        </div>

        <div  data-aos="fade-up" data-aos-delay="900" data-aos-duration="800"   
        class="mt-8 md:mt-4 lg:mt-4 sm:mt-2 flex z-10 flex-col sm:flex-row justify-center items-center">
            <FillButton  class="" >Explora Nuestros Proyectos</FillButton>
            <EmptyButton class=" sm:ml-4 mt-4 sm:mt-0 ">Obtén ayuda personalizada</EmptyButton>
               
        </div>

       <div class="relative mt-10 flex justify-center md:hidden">
            <NuxtImg src="/images/HomePage/Mockup/EmpSystem.png" alt="Mockup mobile"
                class="w-[92vw] max-w-[640px] h-auto object-contain -mt-6" quality="80" />
        </div>


        <div class="absolute bottom-0 left-0 w-full h-24 
           bg-gradient-to-t from-[#5d5d5e] to-transparent">
        </div>




    </section>
</template>