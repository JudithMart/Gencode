<template>
    <section class="relative w-full overflow-hidden
           min-h-fit lg:min-h-screen
           flex flex-col pt-10">
        <!-- Fondo DESKTOP -->
        <NuxtImg src="/images/HomePage/Fondos/CoreServices/Desktop.webp" alt="Servicios web" class="absolute inset-0 w-full h-full object-cover -z-10
             hidden lg:block" format="webp" quality="80" fill />

        <!-- Fondo LAPTOP -->
        <NuxtImg src="/images/HomePage/Fondos/CoreServices/Laptop.webp" alt="Servicios web" class="absolute inset-0 w-full h-full object-cover -z-10
             hidden sm:block lg:hidden" format="webp" quality="80" fill />

        <!-- Fondo MOBILE -->
        <NuxtImg src="/images/HomePage/Fondos/CoreServices/Mobile.jpg"
            class="absolute inset-0 w-full h-full object-cover block md:hidden -z-10" alt="Fondo mobile" format="webp"
            quality="80" />
        <!--  -->
        <div class="relative z-10 flex flex-col items-center text-center px-4">
            <p class="pb-2 text-center font-normal
               bg-gradient-to-b from-text-fromGray to-text-toGray
               bg-clip-text text-transparent
               text-4xl sm:text-6xl md:text-7xl
               max-w-4xl">
                Páginas web
            </p>

            <p class="mt-3 text-white text-center text-base tracking-wider
               max-w-xl">
                Sitios web profesionales a la altura de tu marca,
                <br />
                entendiendo tus necesidades con un estilo rompedor.
            </p>


            <div class="mt-6 flex flex-col sm:flex-row items-center">
                <FillButton>Contáctanos</FillButton>
                <EmptyButton class="sm:ml-4 mt-4 sm:mt-0">
                    Cotiza Tu Proyecto
                </EmptyButton>
            </div>
        </div>
        <div class="relative mt-10 flex justify-center md:hidden">
            <NuxtImg src="/images/HomePage/Mockup/CoreServices.png" alt="Mockup mobile"
                class="w-[92vw] max-w-[640px] h-auto object-contain -mt-6" quality="80" />
        </div>

        <!-- FADE INFERIOR -->
        <div class="pointer-events-none absolute bottom-0 left-0 w-full h-24
             bg-gradient-to-t from-[#79a2b6] to-transparent z-20" />
    </section>
</template>