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
        <div class="w-1/3">
          <h3 class="text-2xl text-center text-blue-400">Pending</h3>
          <ul class="pt-8 space-y-4">
            <li v-for="todo in pending" :key ="todo.id" @click="changeStatus(todo.id)"
              class="w-full px-4 py-2 font-bold text-center text-blue-600 transition-colors duration-500 bg-gray-300 rounded-lg hover:cursor-pointer hover:bg-blue-400 hover:text-gray-200">
              {{todo.content}}
            </li>
          </ul>
        </div>
        <div class="w-1/3">
          <h3 class="text-2xl text-center text-green-400">Completed</h3>
          <ul class="pt-8 space-y-4">
            <li v-for="todo in completed" :key ="todo.id" @click="changeStatus(todo.id)"
              class="w-full px-4 py-2 font-bold text-center text-green-600 transition-colors duration-500 bg-gray-300 rounded-lg hover:cursor-pointer hover:bg-green-400 hover:text-gray-200">
             {{todo.content}}
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>