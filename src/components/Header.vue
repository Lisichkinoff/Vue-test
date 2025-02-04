<template>
  <header class="relative bg-gray-100 mb-20">
    <div class="relative w-full h-[52vw] max-h-[300px] sm:h-48 md:h-64 lg:h-80 xl:h-96 overflow-hidden">
      <picture>
        <source
          media="(min-width: 1200px)"
          srcset="/img/bg-xlarge.png"
          sizes="100vw"
        />
        <source
          media="(min-width: 992px)"
          srcset="/img/bg-large.png"
          sizes="100vw"
        />
        <source
          media="(min-width: 768px)"
          srcset="/img/bg-medium.png"
          sizes="100vw"
        />
        <source
          media="(min-width: 576px)"
          srcset="/img/bg-small.png"
          sizes="100vw"
        />
        <img
          src="/img/bg.png"
          alt="Background"
          class="w-full h-full object-cover absolute inset-0 transition duration-500 ease-in-out"
        />
      </picture>
      <div class="absolute inset-0 bg-black opacity-60 transition duration-500 ease-in-out"></div>
      <div class="absolute inset-0 flex items-center justify-center max-w-screen-xl mx-auto px-4">
        <h1 class="text-white text-center font-bold leading-tight text-[46px] sm:text-[46px] md:text-[54px] lg:text-[62px] w-160">
          Solutions for people like you
        </h1>
      </div>
    </div>
  </header>
</template>

<style scoped>
.bg-black.opacity-50 {
  visibility: hidden;
  opacity: 0;
}
</style>