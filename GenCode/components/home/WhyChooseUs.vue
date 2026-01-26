<script setup>
import { ref } from 'vue'
import FillButton from './FillButton.vue';
import EmptyButton from './EmptyButton.vue';

const activeIndex = ref(0)

const items = [
    {
        label: 'Soporte 24/7',
        image: '/images/HomePage/Images/WhyChooseUs/image.png',
        title: 'Soporte 24/7',
        description: `En Gencode creemos en que no todas
                      las soluciones en el mercado son para ti,
                      nosotros encontraremos justo la que se
                      adecue a tu negocio, en precio, viabilidad
                      y tiempo.`
    },
    {
        label: 'Soluciones reales',
        image: '/images/HomePage/Images/WhyChooseUs/image.png',
        title: 'Soluciones reales para tu negocio',
        description: `Diseñamos sistemas que crecen
                      contigo y con tu empresa,
                      sin soluciones genéricas
                      ni ataduras técnicas.`
    },
    {
        label: 'Entendimiento',
        image: '/images/HomePage/Images/WhyChooseUs/image.png',
        title: 'Entendemos tu negocio',
        description: `Nos involucramos en tus procesos,
                      hablamos tu idioma
                      y proponemos soluciones
                      realmente viables.`
    },
    {
        label: 'Único y personalizado',
        image: '/images/HomePage/Images/WhyChooseUs/image.png',
        title: 'Único y personalizado',
        description: `Cada proyecto es único,
                      diseñado desde cero
                      para ajustarse a tus objetivos
                      y presupuesto.`
    }
]
</script>


<template>
    <section class="bg-fondo-gray w-full py-16">
        <div class="mx-auto w-full max-w-8xl  ">
            <div class="flex flex-col items-center sm:items-start ml-6 md:ml-20  flex-1 2xl:items-center ">
                <p data-aos="zoom-in" data-aos-delay="0" data-aos-duration="800"
                    class="text-center sm:text-left font-normal bg-gradient-to-b from-text-fromGray to-text-toGray bg-clip-text text-transparent 
                           text-4xl sm:text-4xl md:text-3xl lg:text-7xl 2xl:text-7xl  max-w-6xl 2xl:whitespace-nowrap ">
                    ¿Por qué trabajar <span class='hidden lg:inline 2xl:hidden'><br /></span>con nosotros?
                </p>
            </div>

            <!-- ================= MOBILE ================= -->
            <div class="sm:hidden mt-10 px-4">
                <div class="relative rounded-2xl overflow-hidden">

                    <transition name="fade" mode="out-in">
                        <NuxtImg :key="activeIndex" :src="items[activeIndex].image" alt="Ilustración"
                            class="w-full h-[420px] object-cover" />
                    </transition>

                    <div class="absolute inset-0 bg-black/65"></div>

                    <div class="absolute inset-0 flex flex-col justify-between p-6 text-white">
                        <transition name="fade-slide" mode="out-in">
                            <div :key="'text-' + activeIndex">
                                <p class="text-2xl font-semibold">
                                    {{ items[activeIndex].title }}
                                </p>
                                <p class="mt-3 text-sm opacity-90">
                                    {{ items[activeIndex].description }}
                                </p>
                            </div>
                        </transition>

                        <div class="grid grid-cols-2 gap-3 mt-6">
                            <EmptyButton v-for="(item, index) in items" :key="item.label" @click="activeIndex = index"
                                class=" text-sm items-center rounded-lg text-center font-light transition-all duration-300 border" :class="activeIndex === index
                                    ? 'bg-primary border-primary text-white'
                                    : 'bg-white/50 border-white/30'
                                    ">
                                {{ item.label }}
                            </EmptyButton>
                        </div>

                        <div class="mt-2 flex justify-center">
                            <FillButton class="text-sm 2xl:text-xl text-white">
                                Contáctanos
                            </FillButton>
                        </div>
                        </div>
                    </div>

                </div>




                <!-- ================= DESKTOP ================= -->


                <div data-aos="zoom-in" data-aos-delay="900" data-aos-duration="800" class="sm:flex flex-col sm:flex-row w-full justify-center  mt-8 hidden ">
                    <div  class="ml-20 flex justify-center items-center">
                        <transition name="fade-slide" mode="out-in">
                            <NuxtImg :key="activeIndex" :src="items[activeIndex].image" alt="Ilustración" width="600"
                                height="700" class="mt-10 rounded-lg bg-cover  sm:block
                        sm:w-[420px] sm:h-[480px]
                        md:w-[500px] md:h-[580px]
                        lg:w-[500px] lg:h-[500px]" />
                        </transition>
                    </div>

                    <div  class="flex flex-col mt-5">
                        <div class="flex flex-col sm:flex-row justify-center items-center
                          sm:items-start md:items-start lg:items-start
                          sm:ml-6 md:ml-10 lg:ml-14 gap-2 sm:mt-10">
                            <EmptyButton v-for="(item, index) in items" :key="item.label" @click="activeIndex = index"
                                class="  text-xs font-thin 2xl:text-xl transition-all duration-300 border-2"
                                :class="activeIndex === index
                                    ? 'bg-primary text-white border-primary scale-105'
                                    : 'bg-white/10 text-white opacity-60 hover:opacity-100'">
                                {{ item.label }}
                            </EmptyButton>
                        </div>
                        <div class="sm:ml-6 md:ml-10 lg:ml-14 sm:mt-20 ">
                            <transition name="fade-slide" mode="out-in">
                                <div :key="activeIndex">
                                    <p class="text-center sm:text-left font-normal
                                   bg-gradient-to-b from-text-fromGray to-text-toGray
                                   bg-clip-text text-transparent
                                   text-2xl sm:text-3xl md:text-2xl lg:text-5xl 2xl:text-5xl
                                   max-w-6xl">
                                        {{ items[activeIndex].title }}
                                    </p>
                                    <p class="text-center sm:text-left font-light text-white
                                   mt-5 text-lg tracking-wider max-w-6xl whitespace-pre-line">
                                        {{ items[activeIndex].description }}
                                    </p>
                                    <div class="mt-10">
                                        <FillButton class="text-sm 2xl:text-xl">
                                            Contáctanos
                                        </FillButton>
                                    </div>
                                </div>
                            </transition>
                        </div>
                    </div>
                    
                </div>
              
            </div>
    </section>
</template>

<style scoped>
.fade-slide-enter-active,
.fade-slide-leave-active {
    transition: all 0.35s ease;
}

.fade-slide-enter-from {
    opacity: 0;
    transform: translateY(12px);
}

.fade-slide-leave-to {
    opacity: 0;
    transform: translateY(-12px);
}
</style>