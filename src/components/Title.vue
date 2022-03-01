<script setup>
import {ref} from "vue";
const newTodo = ref("");

      const addTodo = (newTodo) => {
        if (newTodo.trim()) {
          todos.value.push({
            id: todos.value.length,
            content: newTodo,
            done: false,
            });
        }
      };

</script>
<template>
         <h1
            class="pb-4 text-6xl font-thin tracking-tight text-center text-gray-300">
            🚀 My Todo App 🚀
        </h1>
        <input 
        @change="add"
        v-model="newTodo"
        type="text"
        class="px-4 py-2 text-xl text-center rounded-lg text-gray-500"
        placeholder="New Todo"
      />
    </template>
