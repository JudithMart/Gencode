<template>
    <div class="relative overflow-hidden lg:min-h-screen w-full pt-10 md:min-h-[85vh] ">
        <NuxtImg src="/images/FCS.png" alt="Mokup servicios"
            class="absolute inset-0 w-full h-full object-cover object-center -z-10" format="webp" quality="80" fill />

        <div class="flex  items-center flex-col ">
            <p class="pb-2 leading-relaxed text-center font-normal bg-gradient-to-b from-[#F8FAFC] to-gray-500 bg-clip-text text-transparent
                text-4xl sm:text-6xl md:text-7xl max-w-4xl whitespace-pre-line ">

                Páginas web
            </p>
            <p class="mt-3 text-[#FFFFFF] text-center text-base  tracking-wider max-w-xl">Sitios web profesionales
                a la altura de tu marca, <br /> entendiendo tus necesidades con un estilo rompedor.</p>
        </div>

        <div class="relative mt-4 flex  flex-col sm:flex-row justify-center items-center z-10 ">
            <FillButton>Contáctanos</FillButton>
            <EmptyButton class="sm:ml-4 mt-4 sm:mt-0">Cotiza Tu Proyecto</EmptyButton>
        </div>
        <div class="flex  justify-center items-center  mb:h-auto lg:h-80 ">
            <NuxtImg src="/images/MCS.png" alt="Mokup servicios" c class="w-full h-auto object-contain -mt-2
         max-w-[90%] md:max-w-[85%] lg:max-w-7xl" format="webp" quality="80" />
        </div>
         <div class="absolute bottom-0 left-0 w-full h-24 
           bg-gradient-to-t from-[#79a2b6] to-transparent">
        </div>

        
    </div>
</template>