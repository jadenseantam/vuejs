<script setup>
import { ref } from 'vue';

let input = ref('')
let tasks = ref([])
document.title = "Todo App"

const addTask = () => {
  if (input.value) {
    tasks.value = [...tasks.value, input.value];
    input.value = ''; 
  }
}
</script>

<template>
  <div class="container">
    <input type="text" v-model="input"> 
    <button @click="addTask">Add Task</button>
    <ul>
      <li v-for="task in tasks">
        {{ task }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
</style>