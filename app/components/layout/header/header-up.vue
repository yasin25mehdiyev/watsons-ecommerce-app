<template>
  <div class="bg-watsons-dark-grey text-white text-sm py-2">
    <div class="max-w-7xl mx-auto px-4 flex items-center justify-between">
      <div class="flex items-center gap-2">
        <NuxtLink to="#" class="flex items-center gap-2 px-4 hover:text-watsons-light/90">
          <Store />
          <span class="text-sm">Stores</span>
        </NuxtLink>

        <NuxtLink to="#" class="flex items-center gap-2 px-4 hover:text-watsons-light/90">
          <Catalog />
          <span class="text-sm">Catalog</span>
        </NuxtLink>
      </div>

      <div class="hidden md:block">
        <p class="text-watsons-smoke text-sm">
          Watsons Beauty and Personal Care Awards Nominees!
        </p>
      </div>

      <a href="tel:+908501234567" class="flex items-center gap-2 hover:text-watsons-light/90 text-sm font-medium">
        <span class="hidden sm:inline">Call us: (+90) 850 123 45 67</span>
        <Phone />
      </a>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { Catalog, Phone, Store } from '@/assets/icons'
</script>
