<template>
    <button class="secondary" @click="emits('setFilter', props.filter)">{{ props.filter }}</button>
</template>

<script>
import { TaskFilter } from './components/types.ts';

const props = defineProps<{
    filter: TaskFilter
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