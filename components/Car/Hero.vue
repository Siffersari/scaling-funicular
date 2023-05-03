<template>
  <div
    class="relative h-screen w-100 bg-no-repeat bg-cover bg-bottom bg-[url('https://assets.whichcar.com.au/image/private/s--Jfxwc9oa--/c_fill,q_auto:good/c_scale,w_3072/t_w_wheels_sw/f_auto/2022_mercedes_benz_a45_amg_hatch_yellow_63.jpg')]"
  >
    <div class="z-10 absolute w-full h-full flex justify-center items-center">
      <div class="text-center w1/2">
        <h1 class="text-8xl font-serif mb-10 text-white">Find your drive</h1>
        <CarSearchBar />
      </div>
    </div>
    <div class="z-1 absolute w-full h-full bg-black opacity-50"></div>
  </div>
</template>
