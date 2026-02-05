<script setup>
import { ref } from 'vue';

document.title = "Tab App"
let currentTab = ref(0)
function changeTab(designatedTab) {
  currentTab.value = designatedTab
}
</script>

<template>
  <div class="page">
    <div class="container">
      <h1>Page title</h1>
      <button @click="changeTab(0)">Default</button>
      <button @click="changeTab(1)">Tab 1</button>
      <button @click="changeTab(2)">Tab 2</button>
      <button @click="changeTab(3)">Tab 3</button><br>
      <p v-if="currentTab === 0">Default Content</p>
      <p v-if="currentTab === 1">Tab 1 Content</p>
      <p v-if="currentTab === 2">Tab 2 Content</p>
      <p v-if="currentTab === 3">Tab 3 Content</p>
    </div>
  </div>
</template>

<style>
.page {
  background: linear-gradient(to left top, rgb(0, 255, 0), rgb(0, 191, 255));
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  background-color: rgba(255, 255, 255, .1);
  padding: 30px;
  border-radius: 20px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, .3);
}
button {
  background-color: rgba(255, 255, 255, .1);
  padding: 10px;
  border-radius: 20px;
  box-shadow: 0 6px 18px rgba(0, 0, 0, .3);
  border: none;
  margin: 5px;
  transition: all .3s ease;
}
button:hover {
    background-color: rgba(255, 255, 255, .4);
}
</style>