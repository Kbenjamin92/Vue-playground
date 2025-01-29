<script setup>
import { ref } from 'vue'

const data = ref(null)
const loading = ref(null)
const error = ref(null)

const fetchData = async () => {
  if (!data.value) {
    try {
      const res = await fetch('https://jsonplaceholder.typicode.com/posts')
      loading.value = true
      if (!res.ok) {
        throw new Error('Faild to fetch')
      }
      data.value = await res.json()
      const limitedApiData = data.value.slice(0, 10)
      data.value = limitedApiData
    } catch (err) {
      error.value = err.message
    } finally {
      loading.value = false
    }
  }
}
</script>

<template>
  <div>
    <h2>Data from API</h2>
    <button class="fetch-button" @click="fetchData">Click me to get api data</button>
    <p v-if="!data">No data yet.</p>
    <p v-else-if="loading">Loading...</p>
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
