<template>
  <header :class="cn('bg-dark-gray')">
    <HeaderUp />
  </header>
</template>

<script setup lang="ts">
import { cn } from '@/utils'
import HeaderUp from './header-up.vue'
</script>
