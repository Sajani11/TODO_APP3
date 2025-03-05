<template>
    <div class="container mt-2">
      <h2>To-Do List</h2>
      <div class="input-group mb-3">
        <input v-model="newTodo" type="text" class="form-control" placeholder="Add new task" @keyup.enter="addTodo" />
        <button @click="addTodo" class="btn btn-primary">Add</button>
      </div>
      <ul class="list-group">
        <li v-for="todo in todos" :key="todo.id" class="list-group-item d-flex justify-content-between">
          <span :class="{ 'text-decoration-line-through': todo.completed }" @click="toggleComplete(todo)">
            {{ todo.title }}
          </span>
          <button @click="deleteTodo(todo.id)" class="btn btn-danger btn-sm">Delete</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  import axios from 'axios'
  
  export default {
    data() {
      return {
        todos: [],
        newTodo: ""
      }
    },
    methods: {
      async fetchTodos() {
        let response = await axios.get("http://127.0.0.1:8000/api/todos/")
        this.todos = response.data
      },
      async addTodo() {
        if (this.newTodo.trim() === "") return;
        await axios.post("http://127.0.0.1:8000/api/todos/", { title: this.newTodo, completed: false })
        this.newTodo = ""
        this.fetchTodos()
      },
      async toggleComplete(todo) {
        await axios.put(`http://127.0.0.1:8000/api/todos/${todo.id}/`, { ...todo, completed: !todo.completed })
        this.fetchTodos()
      },
      async deleteTodo(id) {
        await axios.delete(`http://127.0.0.1:8000/api/todos/${id}/`)
        this.fetchTodos()
      }
    },
    mounted() {
      this.fetchTodos()
    }
  }
  </script>
  