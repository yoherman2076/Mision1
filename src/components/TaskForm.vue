<template>
    <form @submit.prevent="submitForm">
        <label>
            New Task<br>
            <input 
            v-model="newTask" 
            name="newTask" 
            :aria-invalid="!!error || undefined"
            @input="error = ''"
            >
            <small v-if="error" id="invalid-helper">
                {{ error }}
            </small>
        </label>
    </form>
    <div class="button-cont">
        <button>Add Task</button>
    </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const newTask = ref("");
const error = ref("");


const emit = defineEmits<{
    addTask: [newTask: string]
}>();

function submitForm() {
    if (newTask.value.trim()) {
        emit("addTask", newTask.value);
        newTask.value = "";
    } else {
        error.value = "Task can't be empty"
    }
}
</script>

