<template>
    <div class="pending-task">
        <h3>{{ taskTitle }}</h3>
        <button @click="toggleTaskVisibility">{{ show }}</button>
        <div  v-show="viewFullTask">
            <p>The task description</p>
        </div>
    </div>
</template>

<script>
export default {
    name: 'PendingTask',
    data() {
        return {
            taskTitle: 'Task Title',
            viewFullTask: false,
            show: 'show more'
        };
    },
    methods: {
        toggleTaskVisibility() {
            this.viewFullTask = !this.viewFullTask;
            this.show = this.viewFullTask ? 'show less' : 'show more';
        },
    },
};
</script>

<style>
/* Add your component-specific styles here */
</style>
