<template>
<div>
  <h1>Tasky</h1>
  <ul>
    <li v-bind:key="taskItem.id" v-for="taskItem in tasks">
      <TaskItem v-bind:task="taskItem"
                v-on:delete-task="$emit('delete-task', taskItem.id)"
                v-on:edit-task="$emit('edit-task', taskItem.id)"/>
    </li>
  </ul>
</div>
</template>

<script>
import TaskItem from './task-item'
export default {
name: "tasks-list",
  components:{
    TaskItem
  },
  props: [
      "tasks"
  ]
}
</script>

<style scoped>

</style>