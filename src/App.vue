<script setup lang="ts"></script>

<template>
  <div class="flex flex-col p-6 space-y-5 items-center justify-center">
    <h1 class="text-3xl text-green-500">Demo Todo App w/ Vue.js</h1>

    <h3>Your Tasks</h3>
    <form>
      <div class="flex mb-6">
        <input type="text" placeholder="Enter new task" class="p-2.5 mr-5 rounded-md border border-green-500" required/>
        <button type="submit" class="bg-green-600 p-2 rounded-md text-white hover:bg-green-300 transition duration-500">Add Task</button>
      </div>
    </form>
  </div>
</template>
