<template>
  <div id="app">
    <NameCompany v-bind:name="company"/>
    <TasksList v-bind:tasks="tasks"
               v-on:delete-task="deleteTask"/>
    <AddTaskItem v-on:add-task="addTask"/>
  </div>
</template>

<script>
import TasksList from "@/components/tasks-list";
import NameCompany from "@/components/name-company";
import AddTaskItem from "@/components/add-task-item";
export default {
  name: 'App',
  components: {
    AddTaskItem,
    TasksList,
    NameCompany
  },
  data(){
    return{
      tasks:[
        {
          id:1,
          title: 'Study Vue Framework',
          completed: false
        },
        {
          id:2,
          title: 'Study Vue Framework 2',
          completed: false
        },
        {
          id:3,
          title: 'Study Vue Framework 3',
          completed: false
        },
        {
          id:4,
          title: 'Study Vue Framework 4',
          completed: false
        }
      ],
      company: 'dix Agro'
    }
  },
  methods:{
    addTask(newTask){
      this.tasks = [...this.tasks, newTask] // el metodo recibe la tarea y la agrega al array
    },
    deleteTask(taskId){
      this.tasks = this.tasks.filter(task => task.id !== taskId);
    }
  }
}
</script>

<style>
</style>
