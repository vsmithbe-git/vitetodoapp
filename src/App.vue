<script setup>
import {ref} from "vue";
import useTodos from "./composables/useTodos";
const {pending, completed, addTodo, changeStatus,} = useTodos();

const newTodo = ref("");
</script>

<template>
  <div class="min-h-screen bg-gray-800">
    <div class="container flex flex-col pt-8 mx-auto space-y-8">
      <h1
        class="pb-4 text-6xl font-thin tracking-tight text-center text-gray-300">
        🚀 My Todo App 🚀
      </h1>
      <input 
        @change="addTodo(newTodo)"
        v-model="newTodo"
        type="text"
        class="px-4 py-2 text-xl text-center rounded-lg text-gray-500"
        placeholder="New Todo"
      />
      <div class="flex justify-around">
        <List />
        <List isCompleted />
      </div>
    </div>
  </div>
</template>