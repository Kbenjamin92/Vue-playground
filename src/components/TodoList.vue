<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  items: [],
})
</script>

<template>
  <div>
    <ul v-for="item in items">
      <li class="list-items">{{ item.title }}</li>
      <li class="list-items">{{ item.description }}</li>
    </ul>
  </div>
</template>

<style scoped>
.list-items {
  list-style: none;
}
</style>
