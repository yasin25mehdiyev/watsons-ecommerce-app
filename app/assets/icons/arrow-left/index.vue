<template>
  <svg :style="{ width: props.width + 'px', height: props.height + 'px' }" viewBox="0 0 24 24" fill="none"
    xmlns="http://www.w3.org/2000/svg" v-bind="$attrs">
    <path
      d="M15.3438 17.7109C15.1979 17.8568 15.043 17.8568 14.8789 17.7109L9.16406 11.9688C9 11.8229 9 11.6771 9.16406 11.5312L14.8789 5.78906C15.043 5.64323 15.1979 5.64323 15.3438 5.78906L15.8906 6.33594C16.0547 6.48177 16.0547 6.63672 15.8906 6.80078L10.9414 11.75L15.8906 16.6992C16.0547 16.8633 16.0547 17.0182 15.8906 17.1641L15.3438 17.7109Z"
      fill="currentColor" />
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
