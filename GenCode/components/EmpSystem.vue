<template>
    <section class="relative w-full overflow-hidden
            min-h-fit lg:min-h-[95vh]
            flex flex-col pt-10">

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
        <!--  -->
        <div class="flex items-center flex-col px-2 z-10">
            <p class="pb-2  font-light text-center  bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent
                text-4xl sm:text-6xl md:text-7xl max-w-4xl whitespace-pre-line ">

                Sistemas empresariales
            </p>
            <p class="mt-3 px-5 text-[#FFFFFF] text-center text-base  tracking-wider max-w-xl">Soluciones personalizadas
                para
                tu empresa cuando un CRM no es lo que necesitas.</p>
        </div>

        <div class="mt-2 sm:mt-2 flex z-10 flex-col sm:flex-row justify-center items-center">
            <FillButton class="text-sm">Explora Nuestros Proyectos</FillButton>
            <EmptyButton class="sm:ml-4 mt-4 sm:mt-0 text-sm">Obtén ayuda personalizada</EmptyButton>
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