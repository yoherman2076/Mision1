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
        <div class="button-cont">
            <button>Add Task</button>
        </div>
    </form>
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

// Función maniática.
function submitForm() {
    if (!form.newTask.trim()) return form.error = "Task can not be empty."
    emit("addTask", form.newTask);
    form.newTask = "";
}
</script>

