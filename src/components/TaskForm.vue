<template>
    <form @submit.prevent="submitForm">
        <label>
            New Task<br>
            <input 
            v-model="form.newTask" 
            name="newTask" 
            :aria-invalid="!!form.error || undefined"
            @input="form.error = ''"
            >
            <small v-if="form.error" id="invalid-helper">
                {{ form.error }}
            </small>
        </label>
    </form>
    <div class="button-cont">
        <button>Add Task</button>
    </div>
</template>

<script lang="ts" setup>
// import { ref } from 'vue';
import { reactive } from 'vue';

const form = reactive({
    newTask: "",
    error: ""
});

// Versión con ref:
// const newTask = ref("");
// const error = ref("");
// ---

const emit = defineEmits<{
    addTask: [newTask: string]
}>();

function submitForm() {
    if (form.newTask.trim()) {
        emit("addTask", form.newTask);
        form.newTask = "";
    } else {
        form.error = "Task can't be empty"
    }
}
</script>

