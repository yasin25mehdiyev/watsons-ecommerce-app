<template>
  <svg :style="{ width: props.width + 'px', height: props.height + 'px' }" viewBox="0 0 24 24" fill="none"
    xmlns="http://www.w3.org/2000/svg" v-bind="$attrs">
    <path
      d="M9.71094 5.78906C9.85677 5.64323 10.0117 5.64323 10.1758 5.78906L15.8906 11.5312C16.0547 11.6771 16.0547 11.8229 15.8906 11.9688L10.1758 17.7109C10.0117 17.8568 9.85677 17.8568 9.71094 17.7109L9.16406 17.1641C9 17.0182 9 16.8633 9.16406 16.6992L14.1133 11.75L9.16406 6.80078C9 6.63672 9 6.48177 9.16406 6.33594L9.71094 5.78906Z"
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
