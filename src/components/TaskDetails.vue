<script setup>
import { useTaskStore } from '../stores/TaskStore';


const taskStore = useTaskStore()

const props = defineProps({
    task: { 
        type: Object,
        required: true,
    }
})

</script>
<template>
    <div class="task">
        <h2>{{ task.title }}</h2>
        <div class="icons">
            <i class="material-icons" @click="taskStore.deleteTask(task.id)">delete</i>
            <i class="material-icons" :class="{active:task.isFav}" @click="taskStore.toggleFav(task.id)">favorite</i>
        </div>
    </div>
</template>