<template>
  <div class="app">
    <h1>todo</h1>
    <TodoList />
  </div>
</template>

<script setup lang="ts">
import TodoList from './components/TodoList.vue';
</script>

<style>
body {
  background-color: #1e1e1e;
  color: white;
  font-family: Arial, sans-serif;
  padding: 20px;
  text-align: center;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
}

h1 {
  margin-bottom: 20px;
}

ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

input[type="checkbox"] {
  margin-right: 8px;
}

.completed {
  text-decoration: line-through;
}
</style>
