<template>
  <div class="hello">
    <div class="card">
      <h1>{{ msg }}</h1>
      <p>{{ task }}</p>
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
    };
  },
  methods: {
    changeMessage() {
      this.task = 'You changed the task message!';
    }
  }
};
</script>

<style scoped>
/* Background Styling */
.hello {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: linear-gradient(to right, #4b6cb7, #182848);
  padding: 20px;
}

/* Card Styling */
.card {
  background: rgba(255, 255, 255, 0.95);
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0px 5px 15px rgba(0, 0, 0, 0.3);
  text-align: center;
  max-width: 400px;
  width: 100%;
  transition: transform 0.3s ease-in-out;
}

.card:hover {
  transform: scale(1.05);
}

/* Text Styling */
h1 {
  font-size: 32px;
  font-weight: bold;
  color: #333;
}

p {
  font-size: 18px;
  color: #555;
  margin: 15px 0;
}

/* Button Styling */
button {
  background-color: #ff6b6b;
  color: white;
  padding: 12px 20px;
  font-size: 16px;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: 0.3s;
  box-shadow: 0px 3px 6px rgba(0, 0, 0, 0.2);
}

button:hover {
  background-color: #e63946;
  transform: scale(1.1);
}
</style>
