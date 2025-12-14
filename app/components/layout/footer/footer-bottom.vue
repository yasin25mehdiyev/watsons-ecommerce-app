<template>
  <div class="border-t border-watsons-smoke">
    <div class="max-w-7xl mx-auto px-4 py-6">
      <div class="flex flex-col md:flex-row items-center justify-between gap-4">

        <div class="md:flex items-center gap-2 order-2 md:order-1">
          <span class="text-watsons-grey font-medium text-[10px] text-center md:text-left block md:inline mb-2 md:mb-0">
            © WATSONS 2021 ALL RIGHTS RESERVED
          </span>

          <span class="text-watsons-grey text-[10px] font-medium hidden md:block">|</span>

          <span class="text-watsons-grey text-[10px] font-medium text-center md:text-left block md:inline">
            A MEMBER OF CK HUTCHISON HOLDINGS
          </span>
        </div>

        <!-- Social media -->
        <div class="flex items-center gap-3 order-1 md:order-2">
          <a href="#" aria-label="Facebook" class="flex items-center justify-center shadow-md rounded-full">
            <Facebook />
          </a>


          <a href="#" aria-label="Facebook" class="flex items-center justify-center shadow-md rounded-full">
            <Twitter />
          </a>

          <a href="#" aria-label="Facebook" class="flex items-center justify-center shadow-md rounded-full">
            <Instagram />
          </a>

          <a href="#" aria-label="Facebook" class="flex items-center justify-center shadow-md rounded-full">
            <Youtube />
          </a>

          <a href="#" aria-label="Facebook" class="flex items-center justify-center shadow-md rounded-full">
            <Pinterest />
          </a>
        </div>

      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Facebook, Instagram, Pinterest, Store, Twitter, Youtube } from '@/assets/icons';
</script>
