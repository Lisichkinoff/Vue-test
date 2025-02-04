<template>
  <div class="flex-wrap w-full h-120 bg-black flex items-center justify-center mb-20 bg_square">
    <div class="flex flex-col md:flex-row items-center justify-around max-w-screen-xl mx-auto py-10 w-full px-6">
      <div class="text-sky-400 w-full sm:w-130 order-2">
        <h1 class="text-left font-bold leading-tight text-[46px] sm:text-[46px] md:text-[54px] lg:text-[62px] w-full">
          Solutions for people like you
        </h1>
        <p class="text-left mt-4 text-white w-90 text-[18px] sm:text-[18px] md:text-[20px] lg:text-[22px]">
          How can we help your technology and services business develop a revenue engine based on Hubspot?
        </p>
        <div class="flex justify-start gap-4 mt-6 btn mb-10">
          <button class="bg-sky-400 text-white px-4 py-2"><a href="">Call to action</a></button>
          <button class="border border-sky-400 text-white px-4 py-2"><a href="">Call to action</a></button>
        </div>
      </div>


      <div class="flex items-center justify-end w-full md:w-100 h-[52vw] max-h-[380px] sm:h-100 md:h-100 lg:h-80 xl:h-96 overflow-hidden order-1 md:order-2">
        <picture>
          <source media="(min-width: 992px) and (max-width: 1199px)" srcset="/home-pictures/camera-md.jpg" sizes="100vw" />
          <source media="(min-width: 769px) and (max-width: 991px)" srcset="/home-pictures/camera-sm.jpg" sizes="100vw" />
          <source media="(min-width: 576px) and (max-width: 767px)" srcset="/home-pictures/camera-ssm.jpg" sizes="100vw" />
          <source media="(max-width: 575px)" srcset="/home-pictures/camera-xs.jpg" sizes="100vw" />
          <img
            src="/home-pictures/camera-full.jpg"
            alt="Background"
            class="object-cover h-full w-full max-w-full transition duration-500 ease-in-out"
          />
        </picture>
      </div>
    </div>
  </div>
</template>

<style scoped>
@media (min-width: 768px) and (max-width: 991px) {
  .w-90 {
    width: 100%;
  }
  .flex-col {
    flex-direction: column;
  }
  .order-1 {
    order: 2;
    justify-content: center;
    width: 100%;
  }
  .btn {
    justify-content: center;
  }
  .bg_square {
    height: 772px;
  }
  .text-left {
    text-align: center;
  }

}

@media (min-width: 576px) and (max-width: 767px) {
  .mb-10 {
    margin-bottom: 8px;
  }
  .w-90 {
    width: 100%;
  }
  .btn {
    justify-content: center;
  }
  .order-1 {
    order: 2;
    justify-content: center;
    width: 100%;
  }
  .bg_square {
    height: 689px;
  }
   .text-left {
    text-align: center;
  }
}

@media (max-width: 575px) {
  .w-90 {
    width: 100%;
  }
  .btn {
    justify-content: center;
  }
  .order-1 {
    order: 2;
    justify-content: center;
  }
  .bg_square {
    height: 656px;
  }
   .text-left {
    text-align: center;
  }

  .btn {
    flex-direction: column;
  }
}
</style>