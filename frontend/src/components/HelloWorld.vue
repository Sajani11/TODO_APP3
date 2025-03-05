<template>
    <div class="hello">
      <h1>{{ msg }}</h1>
      <div>
        <p>Welcome to the Vue.js To-Do App!</p>
        <button @click="changeMessage">Click me to change the message</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "HelloWorld",
    props: {
      msg: String
    },
    data() {
      return {
        task: 'Do something important',
      }
    },
    methods: {
      changeMessage() {
        this.task = 'You changed the task message!';
      }
    }
  }
  </script>
  
  <style scoped>
  .hello {
    text-align: center;
    margin-top: 50px;
  }
  
  .hello h1 {
    font-size: 36px;
    font-weight: bold;
  }
  
  .hello p {
    font-size: 20px;
    margin-top: 20px;
  }
  
  button {
    background-color: #28a745;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
  }
  
  button:hover {
    background-color: #218838;
  }
  </style>
  