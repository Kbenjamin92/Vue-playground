<script setup>
import { ref } from 'vue'
import TodoList from './TodoList.vue'

const title = ref('')
const description = ref('')
const items = ref([])

const handleSubmit = (event) => {
  event.preventDefault()
  let formObj = {
    id: items.value.length + 1,
    title: title,
    description: description,
  }
  displayItems(formObj)
  title.value = ''
  description.value = ''
}

const displayItems = (object) => {
  let { id, title, description } = object
  const newObject = { title: title._value, description: description._value }
  items.value.push(newObject)
}
</script>

<template>
  <form id="form-container">
    <div id="title-container">
      <label class="input-label" for="">Title</label>
      <input v-model="title" class="todo-input" type="text" />
    </div>
    <div id="description-container">
      <label class="input-label" for="">Description</label>
      <input v-model="description" class="todo-input" type="text" />
    </div>
    <div>
      <button class="submit-button" @click="handleSubmit" type="submit">Add todo</button>
    </div>
  </form>

  <div>
    <TodoList :items="items" />
  </div>
</template>

<style scoped>
#form-container {
  display: flex;
  flex-direction: column;
  gap: 0.7rem;
  margin-top: 4rem;
  padding: 2rem;
}
.input-label {
  font-size: 14px;
}
.todo-input {
  padding: 0.5rem;
  border-radius: 0.2rem;
  border: 1px solid #d3d3d3;
  font-size: 16px;
}

#title-container {
  display: flex;
  flex-direction: column;
}
#description-container {
  display: flex;
  flex-direction: column;
}
.submit-button {
  border: 1px solid teal;
  border-radius: 0.2rem;
  background-color: teal;
  color: aliceblue;
  padding: 0.5rem;
  font-size: 14px;
  font-weight: bold;
}
</style>
