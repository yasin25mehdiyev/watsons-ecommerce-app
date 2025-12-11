<template>
  <section class="py-10 md:py-16">
    <div class="max-w-7xl mx-auto px-4">

      <!-- Title -->
      <div class="flex items-center justify-center mb-10 md:mb-12">
        <div class="flex-1 h-px bg-watsons-light-secondary mt-1.5"></div>

        <h2 class="text-xl md:text-2xl font-semibold text-watsons-teal px-4 md:px-8">
          Featured products
        </h2>

        <div class="flex-1 h-px bg-watsons-light-secondary mt-1.5"></div>
      </div>

      <!-- Products Grid -->
      <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-3 sm:gap-4 md:gap-6 cursor-pointer">

        <div v-for="item in products" :key="item.id"
          class="group relative border border-watsons-smoke rounded-md hover:shadow-lg transition-all">

          <!-- Product Image -->
          <div class="relative bg-watsons-light-smoke">
            <img :src="item.image" :alt="item.title1" class="w-full h-32 sm:h-40 md:h-48 object-contain mb-3 md:mb-4" />

            <!-- Hover desktop buttons -->
            <div class="hidden md:flex absolute bottom-0 left-0 right-0 opacity-0 
                     group-hover:opacity-100 transition-opacity duration-300 
                     h-12 text-white bg-watsons-dark/80 hover:bg-watsons-dark/70 cursor-pointer">
              <div class="flex-1 py-2 text-sm font-medium flex items-center justify-center gap-2">
                <i class="far fa-eye"></i>
                <span>Quick View</span>
              </div>

              <div class="relative flex-1 py-2 text-sm font-medium flex items-center justify-center gap-2">
                <span class="absolute left-0 top-1/2 -translate-y-1/2 h-8 w-[0.5px] bg-watsons-light-smoke"></span>

                <i class="fas fa-shopping-cart"></i>
                <span>Add</span>
              </div>
            </div>
          </div>

          <!-- Product Text -->
          <div class="p-4 md:p-8">
            <p class="text-base sm:text-lg md:text-xl font-bold text-watsons-coal mb-1 md:mb-2">
              {{ item.price }}
            </p>

            <div class="text-watsons-graphene">
              <p>{{ item.title1 }}</p>
              <p>{{ item.title2 }}</p>
            </div>
          </div>

          <!-- Mobile Add Button -->
          <div class="p-4 block border-t border-watsons-smoke md:hidden">
            <button class="bg-watsons-pink hover:bg-pink-600 text-white px-4 py-2 
                     w-full rounded-md font-bold uppercase shadow-lg 
                     transition-all duration-300 hover:scale-105 active:scale-95 
                     flex items-center justify-center gap-2">
              <i class="fas fa-shopping-cart"></i>
              <span>Add</span>
            </button>
          </div>

        </div>

      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import ProductImage1 from '@/assets/image/product/product1.png'
import ProductImage2 from '@/assets/image/product/product2.png'
import ProductImage3 from '@/assets/image/product/product3.png'
import ProductImage4 from '@/assets/image/product/product4.png'

interface Product {
  id: number
  price: string
  title1: string
  title2: string
  image: string
}

const products: Product[] = [
  {
    id: 1,
    price: "44,95 TL",
    title1: "Herbal Science Boom",
    title2: "Butter Hair Care Oil 190 ml",
    image: ProductImage1
  },
  {
    id: 2,
    price: "44,95 TL",
    title1: "Herbal Science Boom",
    title2: "Butter Hair Care Oil 190 ml",
    image: ProductImage2
  },
  {
    id: 3,
    price: "44,95 TL",
    title1: "Herbal Science Boom",
    title2: "Butter Hair Care Oil 190 ml",
    image: ProductImage3
  },
  {
    id: 4,
    price: "44,95 TL",
    title1: "Herbal Science Boom",
    title2: "Butter Hair Care Oil 190 ml",
    image: ProductImage4
  }
]
</script>
