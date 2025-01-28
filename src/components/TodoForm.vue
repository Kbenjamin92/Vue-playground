<script setup></script>

<template>
  <form id="form-container">
    <div id="title-container">
      <label class="input-label" for="">Title</label>
      <input class="todo-input" type="text" />
    </div>
    <div id="description-container">
      <label class="input-label" for="">Description</label>
      <input class="todo-input" type="text" />
    </div>
    <div>
      <button class="submit-button" type="submit">Add todo</button>
    </div>
  </form>
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
