<template>
    <div class="bg-[url('/images/fondo.png')] bg-cover bg-center min-h-screen w-full pt-28">
        <div class="flex items-center justify-center flex-col px-4">
            <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold bg-gradient-to-b from-white to-gray-400 bg-clip-text text-transparent text-center">Evoluciona</h1>
            <h1 class="text-5xl sm:text-7xl md:text-8xl font-bold bg-gradient-to-b from-white to-gray-400 bg-clip-text text-transparent text-center">Soluciones digitales</h1>

            <div class="py-2 max-w-2xl">
                <p class="text-center text-white text-base sm:text-lg">Páginas web profesionales, sistemas empresariales personalizados, SAAS de alta calidad que impulsan tu empresa.<br />Descubre cómo nuestras soluciones personalizadas ayudan a tu negocio.</p>
            </div>

            <div class="pt-6 flex flex-col sm:flex-row items-center">
                <FillButton>Contáctanos</FillButton>
                <EmptyButton class="sm:ml-4 mt-4 sm:mt-0">Cotiza Tu Proyecto</EmptyButton>
            </div>

            <div class="mt-16 sm:mt-20">
                <p class="text-xs sm:text-sm text-center font-thin text-white">Todos nuestros clientes nos<br />recomiendan</p>
            </div>
        </div>

        <div class="flex flex-col md:flex-row items-center justify-center p-5 md:p-7 gap-5 md:gap-18 ">
            <p class="text-xs sm:text-xs font-thin text-white text-center md:text-left max-w-xs md:ml-20">
                <span class="font-medium">Juan Carlos Naranjo CEO de LA BRU </span> <br />
                Trabajar con GENCODE ha sido una gran experiencia. <br /> Son un equipo profesional, proactivo y creativo, con una <br />capacidad de ejecución sobresaliente.
            </p>
            <p class="text-xs sm:text-xs font-thin text-white text-center md:text-left max-w-xs ">
                <span class="font-medium">Eduardo Ramirez CEO de citelis </span> <br />
                Estamos muy satisfechos por la solución tecnológica  que GenCode presentó para nuestra empresa; nos entusiasma <br /> contar con un aliado así para nuestros proyectos futuros
            </p>
        </div>
    </div>
</template>