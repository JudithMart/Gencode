<template>
    <div class="relative min-h-screen w-full pt-24 md:pt-36 xl:pt-44 ">
        <NuxtImg src="images/HomePage/Fondos/Hero/Hero.png" alt="Fondo hero"
            class="absolute inset-0 w-full h-full object-cover object-center -z-10" format="webp" quality="80" fill />
        <div class="flex items-center justify-center flex-col px-6">
            <div class="py-4 ">
                <h1 class=" text-center  font-bold bg-gradient-to-b from-[#F8FAFC] to-gray-500 bg-clip-text text-transparent">
                    <span class="  block text-4xl sm:text-5xl md:text-6xl">Evoluciona</span>
                    <span class="block text-6xl sm:text-7xl md:text-8xl leading-[1.1] pb-4">Soluciones digitales</span>
                </h1>
            </div>


            <div class=" w-full  ">
                <p class="text-center text-white text-base sm:text-sm max-w-4xl mx-auto">Páginas web profesionales,
                    sistemas empresariales personalizados, SAAS de alta calidad que impulsan tu empresa.<br />Descubre
                    cómo nuestras soluciones personalizadas ayudan a tu negocio.</p>
            </div>

            <div class="pt-8 flex flex-col sm:flex-row items-center">
                <FillButton>Contáctanos</FillButton>
                <EmptyButton class="sm:ml-4 mt-4 sm:mt-0">Cotiza Tu Proyecto</EmptyButton>
            </div>

            <div class="mt-20 sm:mt-24">
                <p class="text-xs sm:text-xs text-center font-thin text-white">Todos nuestros clientes
                    nos<br />recomiendan</p>
            </div>
        </div>

        <div class=" flex flex-col md:flex-row items-center justify-center p-3 md:p-4 gap-11 md:gap-15 ">
            <p class="text-xs sm:text-xs font-thin text-[#FFFFFF] text-center md:text-left max-w-xs md:ml-10">
                <span class="font-semibold">Juan Carlos Naranjo CEO de LA BRU </span> <br />
                Trabajar con GENCODE ha sido una gran experiencia. Son un equipo profesional, proactivo y
                creativo, con una <br />capacidad de ejecución sobresaliente.
            </p>
            <p class="text-xs sm:text-xs font-thin text-[#FFFFFF] text-center md:text-left max-w-xs ">
                <span class="font-semibold">Eduardo Ramirez CEO de citelis </span> <br />
                Estamos muy satisfechos por la solución tecnológica que GenCode presentó para nuestra empresa; nos
                entusiasma <br /> contar con un aliado así para nuestros proyectos futuros
            </p>
        </div>
    </div>
</template>