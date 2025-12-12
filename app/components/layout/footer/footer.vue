<template>
  <footer class="pt-8 md:pt-12">
    <div class="max-w-7xl mx-auto px-4">
      <MobileFooter />
      <DesktopFooter />
    </div>

    <FooterBottom />
  </footer>
</template>

<script setup lang="ts">
import MobileFooter from './mobile-footer.vue'
import DesktopFooter from './desktop-footer.vue'
import FooterBottom from './footer-bottom.vue'
</script>
