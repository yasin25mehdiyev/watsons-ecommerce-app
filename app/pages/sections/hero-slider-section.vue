<template>
  <section class="bg-watsons-titan relative overflow-hidden outline-none" tabindex="0" @mouseenter="stopAutoplay"
    @mouseleave="handleMouseLeave" @touchstart="onTouchStart" @touchmove="onTouchMove" @touchend="onTouchEnd"
    @mousedown="onMouseDown" @mousemove="onMouseMove" @mouseup="onMouseUp">
    <!-- LEFT ARROW -->
    <button @click="prev" class="hidden md:flex absolute left-11 top-1/2 -translate-y-1/2 z-30
             w-12 h-12 items-center justify-center
             text-watsons-graphene/80 hover:text-watsons-graphene cursor-pointer">
      <ArrowLeft :width=48 :height=48 />
    </button>

    <!-- RIGHT ARROW -->
    <button @click="next" class="hidden md:flex absolute right-11 top-1/2 -translate-y-1/2 z-30
             w-12 h-12 items-center justify-center
             text-watsons-graphene/80 hover:text-watsons-graphene cursor-pointer">
      <ArrowRight :width=48 :height=48 />
    </button>

    <div class="max-w-7xl mx-auto py-12 md:py-16">
      <div class="grid grid-cols-1 md:grid-cols-2 items-center gap-6 px-6">

        <Transition :name="transitionName" mode="out-in">
          <div :key="current" class="order-2 md:order-1">
            <p class="text-watsons-grey font-bold uppercase text-sm">
              {{ activeSlide.badge }}
            </p>

            <h1 class="text-2xl md:text-4xl font-bold text-watsons-coal mb-4">
              {{ activeSlide.title }}
            </h1>

            <p class="text-watsons-graphene mb-4 max-w-xl">
              {{ activeSlide.description }}
            </p>

            <button
              class="cursor-pointer bg-watsons-pink text-white px-5 py-2 rounded-md
                     font-bold hover:bg-watsons-pink/90 transition-all duration-300 w-full md:w-auto hover:scale-105 active:scale-95"
              @mousedown.stop @touchstart.stop>
              SHOP NOW
            </button>

            <!-- DOTS -->
            <div class="flex items-center justify-center md:justify-start gap-2 mt-10">
              <button v-for="(_, index) in slides" :key="index" class="" @click="goTo(index)">
                <span class="block rounded-full transition-all"
                  :class="cn({ 'w-2 h-2 bg-watsons-dark-grey': index === current }, { 'w-1.5 h-1.5 bg-watsons-dark-grey/40': index !== current })" />
              </button>
            </div>
          </div>
        </Transition>

        <!-- IMAGE -->
        <div class="order-1 md:order-2 flex justify-center md:justify-end">
          <img :src="activeSlide.image" alt="Slide image" class="max-w-[280px] md:max-w-[420px] object-contain"
            draggable="false" />
        </div>

      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue'
import { ArrowLeft, ArrowRight } from '@/assets/icons'
import slideImage from '@/assets/image/slider/slider-right.png'

interface Slide {
  badge: string
  title: string
  description: string
  image: string
}

const slides: Slide[] = [
  {
    badge: 'NATURALS BY WATSONS',
    title: 'The new 2021 collection',
    description:
      'Known as the miracle plant, Aloe Vera helps to nourish and moisturize your hair.',
    image: slideImage
  },
  {
    badge: 'WATSONS BEAUTY',
    title: 'Fresh care for your skin',
    description:
      'Discover gentle formulas designed to keep your skin healthy and radiant.',
    image: slideImage
  },
  {
    badge: 'DAILY ROUTINE',
    title: 'Care that fits your life',
    description:
      'Simple routines, powerful results. Care that moves with you every day.',
    image: slideImage
  }
]

/* STATE */
const current = ref(0)
const activeSlide = computed<Slide>(() => slides[current.value]!)

/* DIRECTION */
type Direction = 'next' | 'prev'
const direction = ref<Direction>('next')

const transitionName = computed(() =>
  direction.value === 'next' ? 'slide-next' : 'slide-prev'
)

/* NAVIGATION */
const next = () => {
  direction.value = 'next'
  current.value = (current.value + 1) % slides.length
}

const prev = () => {
  direction.value = 'prev'
  current.value =
    current.value === 0 ? slides.length - 1 : current.value - 1
}

const goTo = (index: number) => {
  direction.value = index > current.value ? 'next' : 'prev'
  current.value = index
}

/* AUTOPLAY */
const INTERVAL = 4000
let timer: ReturnType<typeof setInterval> | null = null

const startAutoplay = () => {
  stopAutoplay()
  timer = setInterval(next, INTERVAL)
}

const stopAutoplay = () => {
  if (timer) {
    clearInterval(timer)
    timer = null
  }
}

/* DRAG (touch + mouse) */
const dragStartX = ref<number | null>(null)
const dragEndX = ref<number | null>(null)
const DRAG_THRESHOLD = 50

const onDragStart = (x: number) => {
  dragStartX.value = x
  stopAutoplay()
}

const onDragMove = (x: number) => {
  dragEndX.value = x
}

const onDragEnd = () => {
  if (dragStartX.value === null || dragEndX.value === null) return

  const diff = dragStartX.value - dragEndX.value

  if (Math.abs(diff) > DRAG_THRESHOLD) {
    diff > 0 ? next() : prev()
  }

  dragStartX.value = null
  dragEndX.value = null
  startAutoplay()
}

/* TOUCH */
const onTouchStart = (e: TouchEvent) => {
  const touch = e.touches[0]
  if (!touch) return
  onDragStart(touch.clientX)
}

const onTouchMove = (e: TouchEvent) => {
  const touch = e.touches[0]
  if (!touch) return
  onDragMove(touch.clientX)
}

const onTouchEnd = () => {
  onDragEnd()
}

/* MOUSE */
const onMouseDown = (e: MouseEvent) => {
  onDragStart(e.clientX)
}

const onMouseMove = (e: MouseEvent) => {
  if (dragStartX.value === null) return
  onDragMove(e.clientX)
}

const onMouseUp = () => {
  onDragEnd()
}

/* KEYBOARD */
const onKeyDown = (e: KeyboardEvent) => {
  if (e.key === 'ArrowRight') next()
  if (e.key === 'ArrowLeft') prev()
}

const handleMouseLeave = () => {
  onMouseUp()
  startAutoplay()
}

onMounted(() => {
  startAutoplay()
  window.addEventListener('keydown', onKeyDown)
})

onUnmounted(() => {
  stopAutoplay()
  window.removeEventListener('keydown', onKeyDown)
})
</script>

<style scoped>
/* NEXT */
.slide-next-enter-active,
.slide-next-leave-active {
  transition: all 0.4s ease;
}

.slide-next-enter-from {
  opacity: 0;
  transform: translateX(30px);
}

.slide-next-leave-to {
  opacity: 0;
  transform: translateX(-30px);
}

/* PREV */
.slide-prev-enter-active,
.slide-prev-leave-active {
  transition: all 0.4s ease;
}

.slide-prev-enter-from {
  opacity: 0;
  transform: translateX(-30px);
}

.slide-prev-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
</style>
