<template>
  <div class="md:hidden divide-y border-b border-watsons-smoke">

    <div v-for="section in sections" :key="section.title">
      <button class="w-full flex justify-between items-center py-4 font-medium text-watsons-coal"
        @click="toggle(section.title)">
        {{ section.title }}
        <Store :class="cn('transition-transform duration-300', { 'rotate-180': open === section.title })" />
      </button>

      <ul :class="cn(
        'overflow-hidden transition-all duration-300 ease-in-out text-sm text-watsons-graphene',
        {
          'max-h-40 opacity-100 pb-4': open === section.title,
          'max-h-0 opacity-0 pb-0': open !== section.title
        }
      )">
        <li v-for="item in section.items" :key="item" class="py-1">
          <a href="#">{{ item }}</a>
        </li>
      </ul>
    </div>

  </div>
</template>


<script setup lang="ts">
import { ref } from 'vue'
import { Store } from '@/assets/icons'

interface FooterSection {
  title: string
  items: string[]
}

const open = ref<string | null>(null)

const toggle = (title: string) => {
  open.value = open.value === title ? null : title
}

const sections: FooterSection[] = [
  {
    title: 'CORPORATE',
    items: ['About us', 'Press', 'Human resources', 'News from us']
  },
  {
    title: 'SHOPPING',
    items: ['Order and Payment', 'Cancellation and Refund', 'Delivery Conditions', 'Secure shopping']
  },
  {
    title: 'LEGAL',
    items: ['Terms of Use', 'Privacy Policy', 'Membership Agreement', 'Distance Selling Contract']
  },
  {
    title: 'HELP CENTER',
    items: ['FAQ', 'Contact Center']
  }
]
</script>
