<template>
  <div class="hidden md:grid md:grid-cols-6 gap-10 pb-12">

    <FooterColumn title="CORPORATE" :items="['About us', 'Press', 'Human resources', 'News from us']" />

    <FooterColumn title="SHOPPING"
      :items="['Order and Payment', 'Cancellation and Refund', 'Delivery Conditions', 'Secure shopping']" />

    <FooterColumn title="LEGAL"
      :items="['Terms of Use', 'Privacy Policy', 'Membership Agreement', 'Distance Selling Contract']" />

    <FooterColumn title="HELP CENTER" :items="['FAQ', 'Contact center']" />

    <div class="col-span-2">
      <h4 class="font-medium text-watsons-coal text-base mb-8">CONTACT US</h4>

      <ul class="space-y-4 text-sm text-watsons-graphene">
        <li class="flex gap-3">
          <!-- <i class="fas fa-map-marker-alt mt-1" /> -->
          <Store class="mt-1" />
          <span>
            Saray Mah. Site Yolu Cad. Anel İş Merkezi, D:No:5/4,
            34768 Ümraniye/İstanbul
          </span>
        </li>

        <li class="flex gap-3">
          <!-- <i class="fas fa-phone" /> -->
          <Store />
          <a href="tel:08507559987">0850 755 9987</a>
        </li>

        <li class="flex gap-3">
          <!-- <i class="fas fa-envelope" /> -->
          <Store />
          <a href="mailto:info@watsons.com.tr">info@watsons.com.tr</a>
        </li>
      </ul>
    </div>

  </div>
</template>

<script setup lang="ts">
import { Store } from '@/assets/icons';
import FooterColumn from './footer-column.vue'
</script>
