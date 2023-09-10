<script setup>
  const props = defineProps({
    text: String,
    icon: String
  });

  const iconClass = `ph-duotone ph-${props.icon}`
</script>

<template>
  <div class="tag">
    <i :class="iconClass"></i>
    <span class="tag__text">{{ text }}</span>
  </div>
</template>