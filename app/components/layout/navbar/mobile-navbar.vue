<template>
  <!-- Wrapper -->
  <div class="fixed inset-0 z-[999] pointer-events-none">
    <!-- Overlay -->
    <div class="absolute inset-0 bg-watsons-light transition-opacity duration-300"
      :class="cn({ 'opacity-100 pointer-events-auto': isOpen }, { 'opacity-0': !isOpen })" @click="closeMenu" />

    <!-- Menu panel -->
    <div class="absolute left-0 top-0 h-full w-full bg-watsons-light
             transition-transform duration-300 flex flex-col"
      :class="cn({ 'translate-x-0': isOpen }, { 'translate-x-full': !isOpen })">
      <!-- Header -->
      <div class=" flex items-center p-4 border-b bg-watsons-titan">
        <button @click="closeMenu">
          <Close class="text-2xl text-watsons-graphene font-extrabold" />
        </button>

        <span class="ml-auto text-lg font-medium text-watsons-coal">
          Menu
        </span>
      </div>

      <!-- Navigation -->
      <nav class="flex-1 overflow-hidden relative">
        <ul class="absolute inset-0 flex flex-col divide-y font-medium">

          <li v-for="item in menuItems" :key="item.key" class="p-4">
            <button class="w-full flex items-center">
              <ArrowLeft class="text-watsons-graphene" />
              <span class="ml-auto text-lg text-watsons-coal">
                {{ item.label }}
              </span>
            </button>
          </li>

        </ul>
      </nav>

      <!-- Footer -->
      <div class="bg-watsons-smoke/30 divide-y text-watsons-graphene text-sm">
        <div class="flex items-center justify-end gap-4 p-4 font-medium">
          <span>My profile</span>
          <User />
        </div>
        <div class="flex items-center justify-end gap-4 p-4 font-medium">
          <span>Order history</span>
          <History />
        </div>
        <div class="flex items-center justify-end gap-4 p-4 font-medium">
          <span>Help center</span>
          <HelpCenter />
        </div>
        <div class="flex items-center justify-end gap-4 p-4 font-medium">
          <span>Log out</span>
          <Logout />
        </div>
      </div>

    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { Close, ArrowLeft, User, History, HelpCenter, Logout } from '@/assets/icons'

interface MenuItem {
  key: string
  label: string
}

const isOpen = ref<boolean>(false)

const menuItems: MenuItem[] = [
  { key: 'campaigns', label: 'Campaigns' },
  { key: 'personal', label: 'Personal Care' },
  { key: 'skin', label: 'Skin Care' },
  { key: 'makeup', label: 'Make-Up' },
  { key: 'mother', label: 'Mother & Baby' },
  { key: 'healthy', label: 'Healthy Life' },
  { key: 'brands', label: 'Brands' }
]

const openMenu = () => (isOpen.value = true)
const closeMenu = () => (isOpen.value = false)

defineExpose({ openMenu })
</script>
