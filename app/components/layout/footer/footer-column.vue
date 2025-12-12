<template>
  <div>
    <h4 class="font-medium text-watsons-coal text-base mb-8">
      {{ title }}
    </h4>

    <ul class="space-y-2 md:space-y-3">
      <li v-for="item in items" :key="item">
        <a href="#" class="text-watsons-graphene hover:text-watsons-graphene/75 
                 text-sm transition-colors hover:underline">
          {{ item }}
        </a>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  title: string
  items: string[]
}>()
</script>
