<template>
  <div>
    <form @submit="addTask">
      <label for="title">New Task</label>
      <input type="text" v-model="title" name="title" id="title">
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
  name: "add-task-item",
  data(){
    return {
      title: ''
    }
  },
  methods:{
    addTask(e){
      e.preventDefault();

      const newTaskItem = {
        id: uuidv4(),
        title: this.title,
        completed:false
      }
      this.$emit('add-task', newTaskItem);
      this.title='';
    }
  }
}
</script>

<style scoped>

</style>