
<template>
    <section class="relative w-full overflow-hidden
           min-h-fit lg:min-h-screen
           flex flex-col pt-10">
        <!-- Fondo DESKTOP -->
        <NuxtImg src="/images/HomePage/Fondos/SaaSSolutions/Desktop.jpg" alt="Servicios web" class="absolute inset-0 w-full h-full object-cover -z-10
             hidden lg:block" format="webp" quality="80" fill />

        <!-- Fondo LAPTOP -->
        <NuxtImg src="/images/HomePage/Fondos/SaaSSolutions/Laptop.jpg" alt="Servicios web" class="absolute inset-0 w-full h-full object-cover -z-10
             hidden sm:block lg:hidden" format="webp" quality="80" fill />

        <!-- Fondo MOBILE -->
        <NuxtImg src="/images/HomePage/Fondos/SaaSSolutions/Mobile.png"
            class="absolute inset-0 w-full h-full object-cover block md:hidden -z-10" alt="Fondo mobile" format="webp"
            quality="80" />
        <!--  -->
        <div class="relative z-10 flex flex-col items-center text-center px-4">
            <p class="pb-2 text-center font-normal
               bg-gradient-to-b from-text-fromGray to-text-toGray
               bg-clip-text text-transparent
               text-4xl sm:text-6xl md:text-7xl
               max-w-4xl">
                SAAS
            </p>

            <p class="mt-3 text-white text-center text-base tracking-wider
               max-w-xl">
               Nuestras soluciones propias para abogados, tarjetas <br /> de fidelidad y nómina.
            </p>


            <div class="mt-6 flex flex-col sm:flex-row items-center">
                <FillButton>Conoce nuestras SAAS</FillButton>
               
            </div>
        </div>
        <div class="relative mt-10 flex justify-center md:hidden">
            <NuxtImg src="/images/HomePage/Mockup/SaaSSolutions.png" alt="Mockup mobile"
                class="w-[92vw] max-w-[640px] h-auto object-contain -mt-6" quality="80" />
        </div>

        <!-- FADE INFERIOR -->
        <div class="pointer-events-none absolute bottom-0 left-0 w-full h-24
             bg-gradient-to-t from-[#79a2b6] to-transparent z-20" />
    </section>
</template>
