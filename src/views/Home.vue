<template>
  <div class="home">
    <h1>Todo App</h1>
    <div>
      <h3>New Task</h3>
      <div>
        <input v-model="newTask.text">
        <button v-on:click="addTask()">Add Task</button>
      </div>
    </div>
    <ul>
      <li v-for="task in tasks" v-on:click="completeTask(task)">{{ task.text }}</li>
    </ul>
  </div>
</template>

<style>
</style>

<script>
export default {
  data: function() {
    return {
      tasks: [
        {text: "Take out the papers", completed: false},
        {text: "Take out the trash", completed: false},
        {text: "Spend all that spending cash", completed: false}
      ],
      newTask: {text: '', completed: false}
    };
  },
  created: function() {},
  methods: {
    addTask: function() {
      if (this.newTask.text !== "") {
        this.tasks.push(this.newTask);
        this.newTask = {text: "", completed: false};
      }
    },
    completeTask: function(inputTask) {
      var index = this.tasks.indexOf(inputTask);
      this.tasks.splice(index, 1);
    }
  },
  computed: {}
};
</script>











