<template>
  <footer :class="cn('bg-gray-800', 'text-white text-center', 'p-5')">
    <p :class="cn('text-sm text-light-gray', 'font-medium')">Copyright © 2023 - All rights reserved</p>
  </footer>
</template>

<script lang="ts" setup>
import { cn } from '@/utils'
</script>
