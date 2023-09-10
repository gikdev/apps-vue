<script setup>
  const props = defineProps({
    text: String,
    icon: String,
    link: String
  });

  const iconClass = `ph-duotone ph-${props.icon}`
</script>

<template>
  <a class="btn btn--link" :href="link" :title="text">
    <i :class="iconClass"></i>
  </a>
</template>