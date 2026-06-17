<template>
    <div class="task-list">
        <article v-for="task in props.tasks" class="task" :key="task.id">
            <label>
                <input @input="emits('toggleDone', task.id)" :checked="task.done" type="checkbox">
                <span :class="{ done: task.done}">{{ task.title }}</span>
            </label>
            <button @click="emits('removeTask', task.id)" >Remove</button>
        </article>
    </div>
</template>

<script lang="ts" setup>
import type { Task } from './types.ts';

const props = defineProps<{
    tasks: Task[]
}>();

const emits = defineEmits<{
    toggleDone: [id: string];
    removeTask: [id: string];
}>()
</script>

<style>

.task-list {
    margin-top: 1rem;
}

.done {
    text-decoration: line-through;
}

.task {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

</style>