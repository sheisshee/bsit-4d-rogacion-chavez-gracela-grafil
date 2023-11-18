<script setup>
import { ref } from 'vue';

const newColor = ref('');
const colors = ref(['#FDE5D4', '#D6CC99', '#445D48', '#001524', '#22668D', '#EDB7ED', '#82A0D8', '#8DDFCB', '#ECEE81', '#F9DEC9', '#D80032', '#F78CA2']);

const addColor = () => {
  if (newColor.value) {
    colors.value.push(newColor.value);
    newColor.value = '';
  }
};

const removeColor = (index) => {
  colors.value.splice(index, 1);
};
</script>

<template>
   <div>
    <h1>Color Palette</h1>
    <div class="color-form">
      <input type="text" v-model="newColor" @keyup.enter="addColor" placeholder="Enter a color">
      <button @click="addColor">Add Color</button>
    </div>
    <div class="color-list">
      <div v-for="(color, index) in colors" :key="index" class="color-item">
        <div :style="{ backgroundColor: color }" class="color-box"></div>
        <p>{{ color }}</p>
        <button @click="() => removeColor(index)">Remove</button>
      </div>
    </div>
  </div> 
</template>

<style scoped>
 
.body {
  font-family: Arial, sans-serif;
  text-align: center;
  
}

h1 {
  color: #7D5A50;   
  text-align: center;
  margin-top: 0px;
  margin-bottom: 0px;
  text-transform: uppercase;
  background-color: #E5B299;
  padding: 20px;
  font-style: comic sans;
}

.color-form {
  margin: 20px 0;
  text-align: center;
  margin-bottom: 0px;
  padding: 10px; 
}

.color-form input {
  padding: 5px;
}

.color-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}

.color-item {
  margin: 10px;
  text-align: center;
}

.color-box {
  width: 150px;
  height: 150px;
  border: 1px solid #000;
  margin: 0 auto;
  padding: 30px;
  border-radius: 10%;
}

button {
  padding: 5px 10px;
  background-color: #B4846C;
  color: #fff;
  border: none;
  cursor: pointer;
  border-radius: 10px;
}
</style>

  
