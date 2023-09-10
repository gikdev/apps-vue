<script setup>
  import { ref } from 'vue';
  import ToggleBtn from './ToggleBtn.vue'
  import LinkBtn from './LinkBtn.vue'
  import Tag from './Tag.vue'

  const props = defineProps([ 'data' ])
  const {id, icon, name, company, category, website, dlURL, price, platforms } = props.data
  const isOpen = ref(false)

  const toggle = () => isOpen.value = !isOpen.value
</script>

<template>
  <div class="card">
    <div class="card__part card__part--up">
      <img class="card__image" :src="icon" :alt="name">
      <span class="card__name">{{ name }}</span>
      <div class="card__btns">
        <LinkBtn  :href="dlURL" text="install" icon="download-simple" />
        <LinkBtn  :href="website"  text="visit website"  icon="link" />
        <ToggleBtn  :onClick="toggle" :isOpen="isOpen" />
      </div>
    </div>
    <hr v-if="isOpen" class="card__seperator" />
    <div v-if="isOpen" class="card__part card__part--down grid">
      <Tag :text="category" icon="list" />
      <Tag :text="company" icon="buildings" />
      <Tag :text="price" icon="currency-circle-dollar" />
      <Tag :text="platforms" icon="windows-logo" />
    </div>
  </div>
</template>