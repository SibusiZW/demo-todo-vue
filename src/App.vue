<script setup lang="ts">
  import { ref } from 'vue';
  import type { Task } from './types';

  const newTask = ref<string>('');
  const tasks = ref<Task[]>([{
    id: Date.now(),
    title: 'Todo Item',
    completed: false
  }])

  function addTask() {
    if (newTask.value.trim() !== '') {
      tasks.value.push({ id: Date.now(), title: newTask.value, completed: false });
      newTask.value = '';
    }
  }
</script>

<template>
  <div class="flex flex-col p-6 space-y-5 items-center justify-center">
    <h1 class="text-3xl text-green-500">Demo Todo App w/ Vue.js</h1>

    <h3>Your Tasks</h3>
    <form @submit.prevent="addTask">
      <div class="flex mb-6">
        <input v-model="newTask" type="text" placeholder="Enter new task" class="p-2.5 mr-5 rounded-md border border-green-500" required/>
        <button type="submit" class="bg-green-600 p-2 rounded-md text-white hover:bg-green-300 transition duration-500">Add Task</button>
      </div>
    </form>
    
  </div>
</template>
