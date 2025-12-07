<template>
  <svg :style="{ width: props.width + 'px', height: props.height + 'px' }" viewBox="0 0 24 24" fill="none"
    xmlns="http://www.w3.org/2000/svg" v-bind="$attrs">
    <path
      d="M18.5078 5.43359C18.8542 5.50651 19.0273 5.71615 19.0273 6.0625C19.0273 9.5625 17.7878 12.5521 15.3086 15.0312C12.8294 17.5104 9.83984 18.75 6.33984 18.75C5.99349 18.75 5.78385 18.5768 5.71094 18.2305L5.05469 15.3867C4.96354 15.0404 5.09115 14.7943 5.4375 14.6484L8.5 13.3359C8.79167 13.2083 9.04688 13.2721 9.26562 13.5273L10.6055 15.168C11.681 14.6758 12.6289 14.0104 13.4492 13.1719C14.2878 12.3333 14.9531 11.3854 15.4453 10.3281L13.8047 8.96094C13.5495 8.76042 13.4857 8.50521 13.6133 8.19531L14.9258 5.13281C15.0716 4.80469 15.3177 4.6862 15.6641 4.77734L18.5078 5.43359Z"
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
