<script setup>
  defineProps({
    isOpen: Boolean,
    onClick: Function
  });
</script>

<template>
  <button @click="onClick" class="btn btn--toggle">
    <i v-if="isOpen" class="ph-duotone ph-minus-square" title="close"></i>
    <i v-else class="ph-duotone ph-plus-square" title="open"></i>
  </button>
</template>