<template>
  <section class="relative overflow-hidden w-full">

    <!-- Background pattern -->
    <div class="absolute inset-0 bg-cover bg-center bg-no-repeat z-0"
      :style="{ backgroundImage: `url(${OverlayImage})` }">
    </div>

    <div class="relative max-w-7xl mx-auto px-4 py-10 md:py-14 z-10">
      <div class="relative min-h-[280px] md:min-h-[420px] flex items-center justify-center">

        <!-- Left product -->
        <img :src="NiveaImage" alt="Left Product"
          class="hidden md:block absolute md:left-6 bottom-0 md:h-[320px] z-20 pointer-events-none" />

        <!-- Center content -->
        <div class="relative bg-white rounded-tl-[40px] rounded-br-[40px]
                 px-7 md:px-12 py-10 md:py-14 md:ml-10 shadow-sm z-30 text-left">
          <p class="text-watsons-blue font-semibold uppercase tracking-wide">
            EN SEVDİĞİNİZ ÜRÜNLER
          </p>

          <h2 class="text-watsons-blue font-bold uppercase text-[20px]">
            TEK TIKLA KAPINIZDA!
          </h2>

          <div class="mt-3">
            <p class="text-watsons-blue uppercase font-extrabold text-[72px] leading-none">
              60%
            </p>
            <p class="text-watsons-blue uppercase font-extrabold text-[34px]">
              DISCOUNT
            </p>
          </div>

          <button class="mt-6 bg-teal-500 hover:bg-teal-600 text-white px-8 py-3 rounded-md 
                   font-semibold uppercase shadow-lg transition-all duration-300 
                   hover:scale-105 active:scale-95">
            SHOP NOW
          </button>
        </div>

        <!-- Right product -->
        <img :src="NiveaBannerImage" alt="Right Product" class="hidden md:block absolute md:bottom-0 md:right-[170px] md:h-[296px] 
                 z-[99] pointer-events-none" />

      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import OverlayImage from '@/assets/image/overlay.png'
import NiveaImage from '@/assets/image/banner/nivea.png'
import NiveaBannerImage from '@/assets/image/banner/niveaBanner.png'
</script>
