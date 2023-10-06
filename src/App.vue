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
          <button @click="removeColor(index)">Remove</button>
        </div>
      </div>
    </div>
  </template>
  <script>
  export default {
    data() {
      return {
        newColor: '',
        colors: ['#FDE5D4', '#D6CC99', '#445D48', '#001524'],
      };
    },
    methods: {
      addColor() {
        if (this.newColor) {
          this.colors.push(this.newColor);
          this.newColor = '';
        }
      },
      removeColor(index) {
        this.colors.splice(index, 1);
      },
    },
  };
  </script>
  
  <style scoped>
  body {
    font-family: Arial, sans-serif;
    text-align: center;
  }
  
  h1 {
    color: #333;
  }
  
  .color-form {
    margin: 20px 0;
  }
  
  .color-form input {
    padding: 5px;
  }
  
  .color-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .color-item {
    margin: 10px;
    text-align: center;
  }
  
  .color-box {
    width: 50px;
    height: 50px;
    border: 1px solid #000;
    margin: 0 auto;
  }
  
  button {
    padding: 5px 10px;
    background-color: #333;
    color: #fff;
    border: none;
    cursor: pointer;
  }
  </style>
  