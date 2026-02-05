<script setup>
import { ref } from 'vue';

const inputText = ref(''); 
document.title = "Calculator App"

function append(key) {
  inputText.value += key; 
};

const clearInput = () => {
  inputText.value = ''; // Function to clear the input
};

const evaluate = () => {
  try {
    let parsedInput = inputText.value.replace("÷", "/")
    console.log(parsedInput);
    
    inputText.value = eval(parsedInput)
  } catch (error) {
    inputText.value = ""
  }
}
</script>


<template>
  <div class="calculator">
    <div class="container">
      <input readonly="true" :value="inputText">
      <button @click="append('7')">7</button>
      <button @click="append('8')">8</button>
      <button @click="append('9')">9</button>
      <button @click="append('÷')">÷</button>
      <button @click="append('4')">4</button>
      <button @click="append('5')">5</button>
      <button @click="append('6')">6</button>
      <button @click="append('*')">x</button>
      <button @click="append('1')">1</button>
      <button @click="append('2')">2</button>
      <button @click="append('3')">3</button>
      <button @click="append('-')">-</button>
      <button @click="append('.')">.</button>
      <button @click="append('.')">0</button>
      <button @click="append('00')">00</button>
      <button @click="append('+')">+</button>
      <button class="span-two" @click="evaluate()">=</button>
      <button class="span-two" @click="clearInput()">C</button>
    </div>
  </div>
</template>

<style scoped>
.calculator {
  height: calc(100vh - 40px); 
  padding: 20px; 
  background: linear-gradient(to right bottom, rgb(0, 255, 0), rgb(0, 191, 255));
  display: flex;
  justify-content: center;
  align-items: center; 
  margin: -8px;
}

.container {
  padding: 30px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 10px;
  width: 300px;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 40px; 
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
  backdrop-filter: blur(5px); 
}

input {
  grid-column: span 4;
  padding: 20px;
  font-size: 2rem;
  text-align: right;
  border: none;
  border-radius: 10px; 
  margin-bottom: 10px;
  background-color: rgba(255, 255, 255, .3);
}

button {
  padding: 20px;
  font-size: 1.5rem;
  border: none;
  border-radius: 50px; 
  background-color: rgba(255, 255, 255, .1); 
  box-shadow: 0 5px 8px rgba(0, 0, 0, .2);
  color: rgb(0, 0, 0);
  cursor: pointer;
  transition:all ease 0.3s;
}

button:hover {
  background-color: rgba(255, 255, 255, .3); 
}

.span-two  {
  grid-column: span 2;
  background-color: rgba(255, 255, 255, .5);
}
</style>