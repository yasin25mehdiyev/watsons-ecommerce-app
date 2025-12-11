<template>
    <div class="min-h-screen flex flex-col">
        <Header />
        <Navbar />

        <main class="flex-1 w-full">
            <slot />
        </main>
        <Footer />
    </div>
</template>

<script lang="ts" setup>
import { Header, Footer, Navbar } from '@/components/layout'
</script>
