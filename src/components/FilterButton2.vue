<template>
    <button class="secondary" @click="emits('setFilter', props.filter)">{{ props.filter }}</button>
</template>

<script setup lang="ts">
import type { TaskFilter } from './types';

const props = defineProps<{
    filter: TaskFilter;
}>();

const emits = defineEmits<{
    setFilter: [filter: TaskFilter]
}>();

</script>

<style>
button {
    text-transform: capitalize;
}
</style>