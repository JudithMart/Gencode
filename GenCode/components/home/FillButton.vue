<template>
  <NuxtLink
    to="/"
    class="
      inline-flex items-center justify-center
      bg-primary text-white
      px-6 py-2
      min-w-[150px]
      h-[42px]
      rounded-lg
      text-sm
      font-normal
      shadow-lg
      border-2 border-primary
      transition
      hover:bg-transparent hover:text-gray-400
      2xl:min-w-[256px]
    "
  >
    <slot />
  </NuxtLink>
</template>
