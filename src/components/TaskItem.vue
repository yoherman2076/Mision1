<template>
    <article class="task">
        <label>
            <input @input="emits('toggleDone', task.id)" :checked="task.done" type="checkbox">

            <span :class="{ done: task.done }">{{ task.title }}</span>
        </label>

        <button @click="emits('removeTask', task.id)">Remove</button>
    </article>
</template>

<script setup lang="ts">
import type { Task } from '../types/types';

defineProps<{
    task: Task;
}>();

const emits = defineEmits<{
    toggleDone: [id: string];
    removeTask: [id: string];
}>();
</script>

<style scoped>
.done {
    text-decoration: line-through;
}

.task {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
</style>