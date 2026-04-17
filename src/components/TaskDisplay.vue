<script setup lang="ts">
    import type { Task } from '@/types';

    const emit = defineEmits<{
        (e: 'delete', value: number): void
    }>()

    interface TaskDisplayProps {
        task: Task
    }
    const props = defineProps<TaskDisplayProps>();

    function onDelete() {
        emit('delete', props.task.id)
    }
</script>

<template>
    <div class="w-full max-w-[450px] rounded-md p-5 bg-gray-200 border border-zinc-300">
        <p>{{ task.title }}</p>

        <div class="mb-4">
            <p class="bg-green-300 text-green-600 rounded-md p-2" v-if="task.completed">Completed</p>
            <p class="bg-red-300 text-red-600 rounded-md p-2" v-else>Not done yet</p>
        </div>

        <div class="flex">
            <button @click="onDelete" class="bg-red-600 mr-2 transition duration-500 hover:bg-red-300 text-white p-2 rounded-md">Delete</button>
            <button class="bg-blue-600 transition duration-500 hover:bg-blue-300 text-white p-2 rounded-md">Toggle</button>
        </div>
    </div>
</template>