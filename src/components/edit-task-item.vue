<template>
  <div>
    <form @submit="editTask">
      <label for="title">Edit Task {{task.id}}</label>
      <input type="text" v-model="task.title" name="title" id="title">
      <button type="submit">Edit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "edit-task-item",
  props:[
    "task"
  ],
  methods:{
    editTask(e){
      e.preventDefault();

      console.log('editing...');

      /*const newTaskItem = {
        id: uuidv4(),
        title: this.title,
        completed:false
      }
      this.$emit('add-task', newTaskItem);
      this.title='';*/
    }
  }
}
</script>

<style scoped>

</style>