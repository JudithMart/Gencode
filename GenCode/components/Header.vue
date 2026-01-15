<template>
    <div class="fixed top-0 left-0 w-full z-50 bg-transparent flex justify-between p-4">
        <img src="/images/logo.png" alt="Logo" width="120" height="120" class="object-contain" />

        <div>
            <NuxtLink to="/"
                class="mr-4 text-lg font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">
                Nosotros
            </NuxtLink>
            <NuxtLink to="/"
                class="mr-4 text-lg font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">
                Servicios</NuxtLink>
            <NuxtLink to="/"
                class="mr-4 text-lg font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">
                Portafolio</NuxtLink>
            <NuxtLink to="/"
                class="mr-4 text-lg font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">
                Reseñas</NuxtLink>
                <NuxtLink to="/"
                class="mr-4 text-lg font-light text-white underline-offset-4 hover:underline hover:decoration-[#0091FF]">
                Devs</NuxtLink>
        </div>
        
        <div>
           <FillButton>Contáctanos</FillButton>
        </div>
    </div>
</template>