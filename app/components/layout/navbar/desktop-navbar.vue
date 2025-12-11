<template>
  <nav class="hidden md:block">
    <div class="max-w-7xl mx-auto px-4">
      <ul class="flex items-center gap-9 md:justify-between py-4 px-3 
               text-xs md:text-sm font-bold text-watsons-coal whitespace-nowrap 
               min-w-max md:min-w-0">
        <li v-for="item in navItems" :key="item.to">
          <NuxtLink :to="item.to" class="hover:text-watsons-teal transition-colors">
            {{ item.label }}
          </NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>

<script setup lang="ts">
interface NavItem {
  label: string
  to: string
}

const navItems: NavItem[] = [
  { label: "CAMPAIGNS", to: "#" },
  { label: "PERSONAL CARE", to: "#" },
  { label: "SKIN CARE", to: "#" },
  { label: "MAKE - UP", to: "#" },
  { label: "MOTHER & BABY", to: "#" },
  { label: "MEN CARE", to: "#" },
  { label: "HEALTHY LIFE", to: "#" },
  { label: "BRANDS", to: "#" }
]
</script>
