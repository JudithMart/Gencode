<template>
    <section class="bg-fondo-gray w-full py-16">
        <div class="mx-auto w-full max-w-8xl  ">
            <div class="flex flex-col items-center sm:items-start ml-6 md:ml-20  flex-1 2xl:items-center ">
                <p
                    class="text-center sm:text-left font-normal bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent 
                           text-4xl sm:text-4xl md:text-3xl lg:text-7xl 2xl:text-7xl  max-w-6xl 2xl:whitespace-nowrap ">
                    ¿Por qué trabajar <span class='hidden lg:inline 2xl:hidden'><br /></span>con nosotros?
                </p>
            </div>
            <div class="flex flex-col sm:flex-row w-full justify-center  mt-8  ">
                <div class="ml-20  flex justify-center items-center ">
                    <NuxtImg src="/images/HomePage/Images/WhyChooseUs/image.png" alt="Ilustración" width="600"
                        height="700" class="mt-10 rounded-lg bg-cover hidden sm:block 
                            sm:w-[420px] sm:h-[480px] md:w-[500px] md:h-[600px] lg:w-[500px] lg:h-[600px] " />
                </div>
                <div class="flex flex-col sm:flex-row  justify-center items-center sm:items-start md:items-start lg:items-start 
                        sm:ml-6 md:ml-10 lg:ml-14 gap-2 mt-2 sm:mt-10">
                    <EmptyButton class="text-xs font-thin 2xl:text-xl ">
                        Soporte 24/7
                    </EmptyButton>
                    <EmptyButton class=" text-xs font-thin 2xl:text-xl ">
                        Soluciones reales
                    </EmptyButton>
                    <EmptyButton class="text-xs font-thin 2xl:text-xl ">
                        Entendimiento
                    </EmptyButton>
                    <EmptyButton class="text-xs font-thin 2xl:text-xl ">
                        Único y personalizado
                    </EmptyButton>
                </div>
            </div>
        </div>
    </section>
</template>