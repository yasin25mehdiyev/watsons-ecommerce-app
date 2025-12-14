<template>
  <svg :style="{ width: props.width + 'px', height: props.height + 'px' }" viewBox="0 0 24 24" fill="none"
    xmlns="http://www.w3.org/2000/svg" v-bind="$attrs">
    <path
      d="M18.4883 9.31641C18.6341 9.48047 18.6341 9.63542 18.4883 9.78125L12.7461 15.5234C12.6003 15.6693 12.4544 15.6693 12.3086 15.5234L6.56641 9.78125C6.42057 9.63542 6.42057 9.48047 6.56641 9.31641L7.11328 8.79688C7.25911 8.63281 7.41406 8.63281 7.57812 8.79688L12.5273 13.7188L17.4766 8.79688C17.6406 8.63281 17.7956 8.63281 17.9414 8.79688L18.4883 9.31641Z"
      fill="currentColor" fill-opacity="0.4" />
  </svg>
</template>

<script setup lang="ts">
interface IconProps {
  width?: number
  height?: number
}

const props = withDefaults(defineProps<IconProps>(), {
  width: 24,
  height: 24,
})
</script>
