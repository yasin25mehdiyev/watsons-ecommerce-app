<template>
  <div class="border-t border-watsons-smoke">
    <div class="max-w-7xl mx-auto px-4 py-6">
      <div class="flex flex-col md:flex-row items-center justify-between gap-4">

        <!-- Text -->
        <div class="md:flex items-center gap-2 order-2 md:order-1">
          <span class="text-watsons-grey text-xs md:text-sm text-center md:text-left block md:inline mb-2 md:mb-0">
            © WATSONS 2021 ALL RIGHTS RESERVED
          </span>

          <span class="text-watsons-grey text-sm hidden md:block">|</span>

          <span class="text-watsons-grey text-xs md:text-sm text-center md:text-left block md:inline">
            A MEMBER OF CK HUTCHISON HOLDINGS
          </span>
        </div>

        <!-- Social media -->
        <div class="flex items-center gap-3 order-1 md:order-2">
          <a href="#" aria-label="Facebook" class="w-10 h-10 bg-blue-600 hover:bg-blue-700 rounded-full
                   flex items-center justify-center transition-colors shadow-md">
            <!-- <i class="fab fa-facebook-f text-white"></i> -->
            <Store class="text-white" />
          </a>

          <a href="#" aria-label="Twitter" class="w-10 h-10 bg-sky-400 hover:bg-sky-500 rounded-full
                   flex items-center justify-center transition-colors shadow-md">
            <!-- <i class="fab fa-twitter text-white"></i> -->
            <Store class="text-white" />
          </a>

          <a href="#" aria-label="Instagram" class="w-10 h-10 bg-gradient-to-tr from-purple-600 via-pink-600 to-orange-500
                   hover:from-purple-700 hover:via-pink-700 hover:to-orange-600
                   rounded-full flex items-center justify-center transition-all shadow-md">
            <!-- <i class="fab fa-instagram text-white"></i> -->
            <Store class="text-white" />
          </a>

          <a href="#" aria-label="YouTube" class="w-10 h-10 bg-red-600 hover:bg-red-700 rounded-full
                   flex items-center justify-center transition-colors shadow-md">
            <!-- <i class="fab fa-youtube text-white"></i> -->
            <Store class="text-white" />
          </a>

          <a href="#" aria-label="Pinterest" class="w-10 h-10 bg-red-500 hover:bg-red-600 rounded-full
                   flex items-center justify-center transition-colors shadow-md">
            <!-- <i class="fab fa-pinterest-p text-white"></i> -->
            <Store class="text-white" />
          </a>
        </div>

      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { Store } from '@/assets/icons';

</script>
