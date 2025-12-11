<template>
    <!-- Section 1 (full-width background, content centered) -->
    <section class="bg-gray-100 py-20">
        <div class="container px-4 sm:px-6 lg:px-8">
            <h2 class="text-3xl font-bold mb-4">Section 1 Title</h2>
            <p class="text-watsons-pink">Some content here...</p>
        </div>
    </section>

    <!-- Featured Product Section -->
    <FeaturedProductSection />

    <!-- Newsletter Section -->
    <NewsletterSection />

    <!-- Promo Banner Section -->
    <PromoBannerSection />

    <!-- Featured Category Section -->
    <FeaturedCategorySection />
</template>

<script setup lang="ts">
import { FeaturedProductSection, NewsletterSection, PromoBannerSection, FeaturedCategorySection } from '@/pages/sections'
</script>
