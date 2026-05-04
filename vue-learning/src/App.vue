<script setup>
import { ref } from "vue"

const newTask = ref("")
const tasks = ref([])

function addTask() {
  if (!newTask.value.trim()) return
  tasks.value.push(newTask.value)
  newTask.value = ""
}
</script>

<template>
  <main>
    <h1>Vue Practice</h1>

    <input v-model="newTask" placeholder="Enter a new task" />
    <button @click="addTask">Add</button>

    <ul>
      <li v-for="task in tasks" :key="task">
        {{ task }}
      </li>
    </ul>
  </main>
</template>

<style scoped>
main {
  max-width: 520px;
  margin: 40px auto;
  font-family: system-ui, sans-serif;
}

input,
button {
  padding: 8px 10px;
  margin-right: 10px;
}
</style>

