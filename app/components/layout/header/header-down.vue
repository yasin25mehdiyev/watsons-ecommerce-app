<template>
  <header class="py-3 md:py-4 border-b border-gray-100">
    <div class="max-w-7xl mx-auto px-4 flex items-center justify-between gap-2 md:gap-8">

      <NuxtLink to="/">
        <img :src="logoImage" alt="Logo" class="object-contain h-full" />
      </NuxtLink>

      <div class="hidden md:flex items-center justify-center max-w-2xl">
        <div class="relative">
          <!-- <i class="fas fa-search absolute left-4 top-1/2 -translate-y-1/2 text-watsons-grey/40"></i> -->
          <Store class="absolute left-4 top-1/2 -translate-y-1/2 text-watsons-grey/40" />

          <input type="text" placeholder="Write the product or category you are looking for" class="bg-watsons-smoke/30 min-w-[560px] min-h-[42px]
              pl-10 pr-4 border border-watsons-smoke/30 rounded-[32px]
              focus:outline-none focus:border-watsons-grey text-sm" />
        </div>
      </div>

      <div class="flex items-center gap-8 md:gap-4">
        <div class="flex items-center justify-center gap-8">
          <div class="hidden sm:flex items-center gap-4 cursor-pointer">
            <div class="flex items-center justify-center gap-4">
              <div>
                <span class="text-watsons-grey text-sm">Hello,</span>
                <span class="font-medium text-sm">Clara</span>
              </div>

              <img :src="userImage" alt="User" class="w-9 h-9 rounded-full object-cover" />
            </div>

            <span>
              <!-- <i class="fas fa-chevron-down text-watsons-grey/40 text-sm"></i> -->
              <Store class="text-watsons-grey/40 text-sm" />
            </span>
          </div>

          <button class="md:hidden text-watsons-graphene text-lg">
            <!-- <i class="fas fa-search"></i> -->
            <Store />
          </button>

          <div class="relative">
            <NuxtLink to="/checkout" class="relative inline-block">
              <!-- <i class="fas fa-shopping-cart text-lg text-watsons-graphene"></i> -->
              <Store class="text-lg text-watsons-graphene" />

              <span class="absolute -top-2 -right-2 bg-watsons-error text-white font-bold
                  text-[12px] w-4 h-4 rounded-[40px] flex items-center justify-center">
                2
              </span>
            </NuxtLink>
          </div>
        </div>

        <button class="md:hidden text-gray-600 text-xl" @click="openMobileMenu">
          <Store />
        </button>
      </div>
    </div>
  </header>

  <MobileNavigation ref="mobileMenuRef" />
</template>

<script lang="ts" setup>
import { Store } from '@/assets/icons'
import logoImage from '@/assets/image/logo.png'
import userImage from '@/assets/image/user.jpg'
import MobileNavigation from '@/components/layout/navbar/mobile-navbar.vue'

import { ref } from 'vue'

interface MobileMenuRefProps {
  openMenu: () => void
}

const mobileMenuRef = ref<MobileMenuRefProps | null>(null)

const openMobileMenu = () => mobileMenuRef.value?.openMenu()
</script>
