<template>
  <div :class="cn('container', 'grid grid-cols-3 items-center', 'px-4 py-2')">
    <div :class="cn('flex items-center space-x-4', 'text-white')">
      <div :class="cn('flex items-center gap-2')">
        <Store />
        <p :class="cn('text-sm', 'font-medium')">Stores</p>
      </div>
      <div :class="cn('flex items-center gap-2')">
        <Catalog />
        <p :class="cn('text-sm', 'font-medium')">Catalog</p>
      </div>
    </div>

    <div :class="cn('text-center')">
      <h4 :class="cn('text-sm font-medium text-light-gray', 'hidden sm:block')">
        Watsons Beauty and Personal Care Awards Nominees!
      </h4>
    </div>

    <div :class="cn('flex items-center justify-end gap-2', 'text-white')">
      <p :class="cn('text-sm font-medium', 'hidden sm:block')">Call us: (+90) 850 123 45 67</p>
      <Phone />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { cn } from '@/utils'
import { Catalog, Phone, Store } from '@/assets/icons'
</script>
