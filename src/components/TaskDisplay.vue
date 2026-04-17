<script setup lang="ts">
    import type { Task } from '@/types';

    interface TaskDisplayProps {
        task: Task
    }

    defineProps<TaskDisplayProps>();
</script>

<template>
    <div class="w-full max-w-[450px] rounded-md p-5 bg-gray-200 border border-zinc-300">
        <p>{{ task.title }}</p>
    </div>
</template>