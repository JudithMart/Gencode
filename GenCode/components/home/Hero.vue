<script setup lang="ts">
import EmptyButton from './EmptyButton.vue';
import FillButton from './FillButton.vue';

</script>

<template>
    <div class="relative min-h-screen w-full pt-24 md:pt-36 xl:pt-44 ">


        <!-- Fondo DESKTOP -->
        <NuxtImg src="/images/HomePage/Fondos/Hero/Desktop.jpg" alt="Mokup servicios" class="absolute inset-0 w-full h-full object-cover object-center -z-10
             hidden lg:block" format="webp" quality="80" fill />


        <!-- Fondo LAPTOP -->
        <NuxtImg src="/images/HomePage/Fondos/Hero/Laptop.jpg" alt="Servicios web" class="absolute inset-0 w-full h-full object-cover -z-10 object-center
             hidden sm:block lg:hidden" format="webp" quality="80" fill />

        <!-- Fondo MOBILE -->
        <NuxtImg src="/images/HomePage/Fondos/Hero/Desktopp.jpg"
            class="absolute inset-0 w-full h-full object-cover object-center block md:hidden -z-10" alt="Fondo mobile"
            format="webp" quality="80" />

        <div class="flex items-center justify-center flex-col px-6">

            <!-- TEXTO PRINCIPAL-->
            <div class="md:py-6 pt-10 ">
                <h1 class="text-center font-bold">

                    <span data-aos="fade-down" data-aos-duration="800" data-aos-delay="0" class="block font-medium 
                           text-4xl
                           sm:text-4xl
                           md:text-4xl
                           lg:text-6xl
                           tracking-tight
                           bg-gradient-to-b from-text-fromGray to-text-toGray
                           bg-clip-text text-transparent">
                        Evoluciona
                    </span>

                    <span data-aos="fade-up" data-aos-duration="800" data-aos-delay="900" class="block 
                       text-6xl
                       sm:text-6xl
                       md:text-6xl
                       lg:text-8xl
                       leading-tight
                       py-2 bg-gradient-to-b from-text-fromGray to-text-toGray
                       bg-clip-text text-transparent">
                        Soluciones digitales
                    </span>
                </h1>
            </div>
            <!-- TEXTO -->
            <div class=" mt-5 md:mt-0 w-full " data-aos="fade-up" data-aos-delay="900" data-aos-duration="800">
                <p class="text-center text-white 
                   text-xs
                   sm:text-sm 
                   md:text-base
                    max-w-md sm:max-w-2xl md:max-w-4xl mx-auto">
                    Páginas web profesionales,
                    sistemas empresariales personalizados, SAAS de alta calidad que impulsan tu empresa. Descubre
                    cómo nuestras soluciones personalizadas ayudan a tu negocio.</p>
            </div>

            <div class="pt-8 flex flex-col sm:flex-row items-center text-base mt-4 md:mt-0" data-aos="fade-up" data-aos-delay="700"
                data-aos-duration="1000">
                  <FillButton class="">Contáctanos</FillButton>
                <EmptyButton class="sm:ml-4 mt-4 sm:mt-0 text-xs md:text-sm">
                    Cotiza Tu Proyecto
                </EmptyButton>
            </div>

            <!-- TEXTO FINAL-->
            <div class="mt-20 md:mt-24 sm:mt-24" data-aos="fade-up" data-aos-delay="1000" data-aos-duration="800">
                <p class="text-xs sm:text-xs text-center font-thin text-white">Todos nuestros clientes
                    nos<br />recomiendan</p>
            </div>
        </div>

        <div class=" flex flex-col md:flex-row items-center justify-center 
                    p-3 md:p-4 gap-3 mt-6 md:mt-0 md:gap-15 ">
            <p class="text-xs sm:text-xs font-thin text-[#FFFFFF] text-center md:text-left max-w-xs md:ml-10"
                data-aos="fade-right" data-aos-delay="1000" data-aos-duration="800">
                <span class="font-semibold">Juan Carlos Naranjo CEO de LA BRU </span> <br />
                Trabajar con GENCODE ha sido una gran experiencia. Son un equipo profesional, proactivo y
                creativo, con una <br />capacidad de ejecución sobresaliente.
            </p>
            <p class="text-xs sm:text-xs font-thin text-[#FFFFFF] text-center md:text-left max-w-xs"
                data-aos="fade-left" data-aos-delay="1000" data-aos-duration="800">
                <span class="font-semibold">Eduardo Ramirez CEO de citelis </span> <br />
                Estamos muy satisfechos por la solución tecnológica que GenCode presentó para nuestra empresa; nos
                entusiasma <br /> contar con un aliado así para nuestros proyectos futuros
            </p>
        </div>
    </div>
</template>
