<template>
    <div class="task-list">
        <TaskItem
            v-for="task in props.tasks"
            :key="task.id"
            :task="task"
            @toggle-done="emits('toggleDone', $event)"
            @remove-task="emits('removeTask', $event)"
        />
    </div>
</template>

<script lang="ts" setup>
import type { Task } from './types';
import TaskItem from './TaskItem.vue'

const props = defineProps<{
    tasks: Task[];
}>();

const emits = defineEmits<{
    toggleDone: [id: string];
    removeTask: [id:string];
}>();
</script>
