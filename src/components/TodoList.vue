<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  items: [],
})
</script>

<template>
  <div>
    <ul id="list-container" v-for="item in items">
      <li class="list-items">{{ item.title }}</li>
      <li class="list-items">{{ item.description }}</li>
      <button class="delete-button">delete</button>
    </ul>
  </div>
</template>

<style scoped>
#list-container {
  border: 1px solid #d3d3d3;
  border-radius: 0.5rem;
}
.list-items {
  list-style: none;
}

.delete-button {
  border: 1px solid crimson;
  border-radius: 0.2rem;
  background-color: crimson;
  color: aliceblue;
  padding: 0.5rem;
  font-size: 14px;
  font-weight: bold;
}
</style>
