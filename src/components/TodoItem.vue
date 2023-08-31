<template>
  <li :class="{ completed: todo.completed }">
    {{ todo.text }}
    <button @click="deleteTodo">Delete</button>
  </li>
</template>

<script setup lang="ts">
import { defineProps, defineEmits } from 'vue';

const props = defineProps<{ todo: Todo }>();
const emits = defineEmits();

const todo = props.todo;

function deleteTodo() {
  emits('delete', todo.id);
}
</script>

<style>
.completed {
  text-decoration: line-through;
}
</style>
