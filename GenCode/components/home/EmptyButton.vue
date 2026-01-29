<template>
  <NuxtLink
    to="/"
    class="
      inline-flex items-center justify-center
      bg-transparent text-white
      px-6 py-2
      min-w-[150px]
      h-[42px]
      rounded-lg
      font-normal
      text-sm
      shadow-lg
      border-2 border-primary
      transition
      hover:bg-primary
      2xl:min-w-[256px]
    "
  >
    <slot />
  </NuxtLink>
</template>
