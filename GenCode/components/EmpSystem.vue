<template>
    <div class="relative w-full overflow-hidden
            min-h-fit lg:min-h-[95vh]
            flex flex-col pt-14">
        <NuxtImg src="/images/FES.png" alt="Mokup servicios"
            class="absolute inset-0 w-full h-full object-cover object-center -z-10" format="webp" quality="80" fill />

        <div class="flex items-center flex-col px-2 z-10">
            <p class="pb-2  font-light text-center  bg-gradient-to-b from-[#F8FAFC] to-gray-500 bg-clip-text text-transparent
                text-4xl sm:text-6xl md:text-7xl max-w-4xl whitespace-pre-line ">

                Sistemas empresariales
            </p>
            <p class="mt-3 px-5 text-[#FFFFFF] text-center text-base  tracking-wider max-w-xl">Soluciones personalizadas
                para
                tu empresa cuando un CRM no es lo que necesitas.</p>
        </div>

        <div class="mt-2 sm:mt-2 flex z-10 flex-col sm:flex-row justify-center items-center">
            <FillButton>Explora Nuestros Proyectos</FillButton>
            <EmptyButton class="sm:ml-4 mt-4 sm:mt-0">Obtén ayuda persoonalizada</EmptyButton>
        </div>
        <div class="mt-6 sm:mt-10 lg:mt-auto flex justify-center ">
            <NuxtImg src="/images/MES.png" alt="Mockup empresariales" class="w-full object-contain
         max-w-[100%] md:max-w-[95%] lg:max-w-7xl" format="webp" quality="80" />
        </div>

        <div class="absolute bottom-0 left-0 w-full h-24 
           bg-gradient-to-t from-[#0f0e0e] to-transparent">
        </div>




    </div>
</template>