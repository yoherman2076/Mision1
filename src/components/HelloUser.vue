<script setup lang="ts">
import { ref } from 'vue'
const greeting = ref('Hola, usuario')

function changeGreeting(): void {
    greeting.value = 'Hola, Herman'
}
</script>

<template>
    <div>
        <h1>{{ greeting }}</h1>
        <button @click="changeGreeting">
            Cambiar saludo
        </button>
    </div>
</template>