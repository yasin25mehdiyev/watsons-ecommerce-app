<template>
    <div class="min-h-screen flex flex-col">
        <Header />
        <main class="flex-1 w-full">
            <slot />
        </main>
        <Footer />
    </div>
</template>

<script lang="ts" setup>
import { Header, Footer } from '@/components/layout'
</script>
