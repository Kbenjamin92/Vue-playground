<script setup>
import { ref, onMounted } from 'vue'

const data = ref(null)
const loading = ref(true)
const error = ref(null)

const fetchData = async () => {
  if (!data.value) {
    try {
      const res = await fetch('https://jsonplaceholder.typicode.com/posts')
      if (!res.ok) {
        throw new Error('Faild to fetch')
      }
      data.value = await res.json()
      const limitedApiData = data.value.slice(0, 10)
      data.value = limitedApiData
    } catch (err) {
      error.value = err.message
    } finally {
      loading.value
    }
  }
}
</script>

<template>
  <div>
    <h2>Data from API</h2>
    <button @click="fetchData">Click me to get api data</button>

    <ul>
      <li v-for="item in data" :key="item.id">{{ item.title }}</li>
    </ul>
  </div>
</template>

<style scoped>
.fetch-button {
  border: 1px solid teal;
  border-radius: 0.2rem;
  background-color: teal;
  color: aliceblue;
  padding: 0.5rem;
  font-size: 14px;
  font-weight: bold;
}

li {
  list-style: none;
}
</style>
