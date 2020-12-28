<template>
  <div v-bind:class="{ 'completed': task.completed }">
    <p v-on:click="markCompleted">{{task.title}}</p>
    <p>{{task.id}}</p>
    <button @click="$emit('delete-task', task.id)">Delete</button>
    <button @click="$emit('edit-task', task.id)">Edit</button>
  </div>
</template>

<script>

export default {
  name: "task-item",
  props:[
      "task"
  ],
  methods:{
    markCompleted(){
      this.task.completed = !this.task.completed;
    }
  }
}
</script>

<style scoped>
  .completed{
    text-decoration: line-through;
  }
</style>