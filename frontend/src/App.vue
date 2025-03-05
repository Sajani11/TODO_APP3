<script setup>
import { RouterView } from 'vue-router'
</script>

<template>
  <div class="app-container">
    <div class="content-card">
      <RouterView />
    </div>
  </div>
</template>

<style scoped>
/* Gradient Background */
body {
  background: linear-gradient(to right, #6a11cb, #2575fc);
  color: white;
  font-family: 'Poppins', sans-serif;
}

/* Centered App Container */
.app-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  padding: 20px;
}

/* Content Card */
.content-card {
  background: rgba(255, 255, 255, 0.9); /* Semi-transparent white */
  color: #333;
  padding: 20px;
  border-radius: 15px;
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.2);
  max-width: 800px;
  width: 100%;
}

/* Navigation Styling */
nav {
  text-align: center;
  margin-bottom: 15px;
}

nav a {
  color: #2575fc;
  text-decoration: none;
  font-weight: bold;
  padding: 10px 15px;
  border-radius: 5px;
  transition: 0.3s;
}

nav a:hover {
  background-color: #2575fc;
  color: white;
}

/* Responsive Design */
@media (max-width: 768px) {
  .content-card {
    padding: 15px;
  }
}
</style>
