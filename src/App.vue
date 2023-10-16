<template>
  <div class="main">
    <header>
      <h1>{{ title }}</h1>
    </header>
    <hr>
  </div>

  <div class="app">
    <button @click="AddTaskMenu">Add Task</button>
    <AddTask v-show="ShowAddTask" @close="EndTask" @added="AddTask"/>
  </div>

  <div class="alert" v-if="tasks.length === 0">
    <h2>No pending tasks</h2>
  </div>

<div class="body">
<ul class="list-group" v-if="tasks.length > 0">
  <li class="list-group-item" v-for="(tasks, index) in tasks" :key="tasks">{{ tasks }} {{ index + 1 }}</li>
</ul>
</div>
</template>

<script>
import AddTask from './components/AddTask.vue';
export default {
  name: 'App',
  components: {
    AddTask
  },
  data() {
    return {
      ShowAddTask : false,
      title : "To Do List",
      taskTitle: '',
      tasks : [],
      enteredTaskTitle: '',
    }
  },
  methods: {
    EndTask() {
      this.ShowAddTask = false,
      this.tasks -= 1
    },
    AddTask() {
      this.ShowAddTask = false,
      this.tasks.push(this.enteredTaskTitle)
      console.log(this.tasks)
    },
    AddTaskMenu() {
      this.ShowAddTask=true;
    },
    onTaskTitleAdded(title) {
      this.taskTitle = title;
      console.log(this.taskTitle)
    },

  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
}

header{
  margin-bottom: 3px;
}

.list-group{
  list-style-type: none;
}
</style>
