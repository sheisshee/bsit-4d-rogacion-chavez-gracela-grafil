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
          <button @click="removeColor(index)">Remove
            <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-cup-hot-fill" viewBox="0 0 16 16">
  <path fill-rule="evenodd" d="M.5 6a.5.5 0 0 0-.488.608l1.652 7.434A2.5 2.5 0 0 0 4.104 16h5.792a2.5 2.5 0 0 0 2.44-1.958l.131-.59a3 3 0 0 0 1.3-5.854l.221-.99A.5.5 0 0 0 13.5 6H.5ZM13 12.5a2.01 2.01 0 0 1-.316-.025l.867-3.898A2.001 2.001 0 0 1 13 12.5Z"/>
  <path d="m4.4.8-.003.004-.014.019a4.167 4.167 0 0 0-.204.31 2.327 2.327 0 0 0-.141.267c-.026.06-.034.092-.037.103v.004a.593.593 0 0 0 .091.248c.075.133.178.272.308.445l.01.012c.118.158.26.347.37.543.112.2.22.455.22.745 0 .188-.065.368-.119.494a3.31 3.31 0 0 1-.202.388 5.444 5.444 0 0 1-.253.382l-.018.025-.005.008-.002.002A.5.5 0 0 1 3.6 4.2l.003-.004.014-.019a4.149 4.149 0 0 0 .204-.31 2.06 2.06 0 0 0 .141-.267c.026-.06.034-.092.037-.103a.593.593 0 0 0-.09-.252A4.334 4.334 0 0 0 3.6 2.8l-.01-.012a5.099 5.099 0 0 1-.37-.543A1.53 1.53 0 0 1 3 1.5c0-.188.065-.368.119-.494.059-.138.134-.274.202-.388a5.446 5.446 0 0 1 .253-.382l.025-.035A.5.5 0 0 1 4.4.8Zm3 0-.003.004-.014.019a4.167 4.167 0 0 0-.204.31 2.327 2.327 0 0 0-.141.267c-.026.06-.034.092-.037.103v.004a.593.593 0 0 0 .091.248c.075.133.178.272.308.445l.01.012c.118.158.26.347.37.543.112.2.22.455.22.745 0 .188-.065.368-.119.494a3.31 3.31 0 0 1-.202.388 5.444 5.444 0 0 1-.253.382l-.018.025-.005.008-.002.002A.5.5 0 0 1 6.6 4.2l.003-.004.014-.019a4.149 4.149 0 0 0 .204-.31 2.06 2.06 0 0 0 .141-.267c.026-.06.034-.092.037-.103a.593.593 0 0 0-.09-.252A4.334 4.334 0 0 0 6.6 2.8l-.01-.012a5.099 5.099 0 0 1-.37-.543A1.53 1.53 0 0 1 6 1.5c0-.188.065-.368.119-.494.059-.138.134-.274.202-.388a5.446 5.446 0 0 1 .253-.382l.025-.035A.5.5 0 0 1 7.4.8Zm3 0-.003.004-.014.019a4.077 4.077 0 0 0-.204.31 2.337 2.337 0 0 0-.141.267c-.026.06-.034.092-.037.103v.004a.593.593 0 0 0 .091.248c.075.133.178.272.308.445l.01.012c.118.158.26.347.37.543.112.2.22.455.22.745 0 .188-.065.368-.119.494a3.198 3.198 0 0 1-.202.388 5.385 5.385 0 0 1-.252.382l-.019.025-.005.008-.002.002A.5.5 0 0 1 9.6 4.2l.003-.004.014-.019a4.149 4.149 0 0 0 .204-.31 2.06 2.06 0 0 0 .141-.267c.026-.06.034-.092.037-.103a.593.593 0 0 0-.09-.252A4.334 4.334 0 0 0 9.6 2.8l-.01-.012a5.099 5.099 0 0 1-.37-.543A1.53 1.53 0 0 1 9 1.5c0-.188.065-.368.119-.494.059-.138.134-.274.202-.388a5.446 5.446 0 0 1 .253-.382l.025-.035A.5.5 0 0 1 10.4.8Z"/>
</svg></button>       
        </div>
      </div>
    </div>
  </template>
  <script>
  export default {
    data() {
      return {
        newColor: '',
        colors: ['#FDE5D4', '#D6CC99', '#445D48', '#001524', '#22668D', '#EDB7ED', '#82A0D8', '#8DDFCB', '#ECEE81', '#F9DEC9', '#D80032', '#F78CA2', ],
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
    color: #7D5A50;   
    text-align: center;
    margin-top: 0px;
    margin-bottom: 0px;
    text-transform: uppercase;
    background-color: #E5B299;
    padding: 20px;
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
  