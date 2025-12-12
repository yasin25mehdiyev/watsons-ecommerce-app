<template>
  <section class="py-10 md:py-16 bg-white">
    <div class="max-w-4xl mx-auto px-4">

      <div class="flex items-center justify-center mb-10 md:mb-12">
        <div class="flex-1 h-px bg-watsons-light-secondary mt-1.5"></div>
        <h2 class="text-xl md:text-2xl font-semibold text-watsons-teal px-4 md:px-8">
          Featured categories
        </h2>
        <div class="flex-1 h-px bg-watsons-light-secondary mt-1.5"></div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-x-10 gap-y-8 justify-center">
        <div v-for="item in categories" :key="item.id" class="group relative h-[260px] overflow-hidden cursor-pointer">
          <img :src="item.image" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105 
                   rounded-md border border-watsons-smoke" />

          <div class="absolute inset-0 bg-black/0 group-hover:bg-black/40 transition-colors duration-300"></div>

          <div class="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 
                   transition-opacity duration-300">
            <div class="bg-watsons-light rounded-xl px-6 py-5 text-center md:max-w-[232px] shadow-md">
              <h3 class="text-lg font-semibold text-gray-800 mb-2">{{ item.title }}</h3>
              <p class="text-gray-600 text-sm mb-4">{{ item.description }}</p>

              <button class="relative cursor-pointer z-10 bg-watsons-teal text-white px-5 py-2 rounded font-medium text-sm
                       transition-all duration-300 hover:bg-teal-600 hover:scale-105 active:scale-95">
                BROWSE
              </button>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>


<script setup lang="ts">
import CategoryImage1 from '@/assets/image/backgrounds/bg1.jpg'
import CategoryImage2 from '@/assets/image/backgrounds/bg2.jpg'
import CategoryImage3 from '@/assets/image/backgrounds/bg3.jpg'
import CategoryImage4 from '@/assets/image/backgrounds/bg4.jpg'

interface Category {
  id: number
  title: string
  description: string
  image: string
}

const categories: Category[] = [
  {
    id: 1,
    title: "Personal Care",
    description: "Lorem ipsum dolor sit amet consectetu elit aliquam",
    image: CategoryImage1
  },
  {
    id: 2,
    title: "Skin Care",
    description: "Lorem ipsum dolor sit amet consectetu elit aliquam",
    image: CategoryImage2
  },
  {
    id: 3,
    title: "Make-Up",
    description: "Lorem ipsum dolor sit amet consectetu elit aliquam",
    image: CategoryImage3
  },
  {
    id: 4,
    title: "Mother & Baby",
    description: "Lorem ipsum dolor sit amet consectetu elit aliquam",
    image: CategoryImage4
  }
]
</script>
