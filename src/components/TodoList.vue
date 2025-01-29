<script setup>
import { defineProps } from 'vue'

const props = defineProps({
  items: [],
})
</script>

<template>
  <div>
    <ul id="list-container" v-for="item in items">
      <li class="list-items-title">{{ item.title }}</li>
      <hr />
      <li class="list-items-des">{{ item.description }}</li>
      <hr />
      <button class="delete-button">delete</button>
    </ul>
  </div>
</template>

<style scoped>
#list-container {
  border: 1px solid #d3d3d3;
  border-radius: 0.5rem;
}
.list-items-title {
  list-style: none;
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 0.5rem;
  margin-top: 0.5rem;
}
.list-items-des {
  list-style: none;
  margin-bottom: 0.5rem;
  margin-top: 0.5rem;
}
.delete-button {
  border: 1px solid crimson;
  border-radius: 0.2rem;
  background-color: crimson;
  color: aliceblue;
  padding: 0.5rem;
  margin-bottom: 0.5rem;
  margin-top: 0.5rem;
  font-size: 14px;
  font-weight: bold;
}
</style>
