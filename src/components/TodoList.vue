<template>
    <div>
      <input v-model="newTodo" @keyup.enter="addTodo" placeholder="Add a new task..." />
      <ul>
        <TodoItem v-for="todo in todos" :key="todo.id" :todo="todo" @delete="deleteTodo" />
      </ul>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref } from 'vue';
  import TodoItem from './TodoItem.vue';
  
  interface Todo {
    id: number;
    text: string;
    completed: boolean;
  }
  
  const todos = ref<Todo[]>([]);
  
  const newTodo = ref('');
  
  function addTodo() {
    if (newTodo.value.trim() !== '') {
      todos.value.push({
        id: todos.value.length + 1,
        text: newTodo.value,
        completed: false,
      });
      newTodo.value = '';
    }
  }
  
  function deleteTodo(todoId: number) {
    todos.value = todos.value.filter(todo => todo.id !== todoId);
  }
  </script>
  