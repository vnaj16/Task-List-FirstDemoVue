<template>
  <div id="app">
    <NameCompany v-bind:name="company"/>
    <TasksList v-bind:tasks="tasks"
               v-on:delete-task="deleteTask"
                v-on:edit-task="editTask"/>
    <AddTaskItem v-on:add-task="addTask"/>
    <br/>
    <EditTaskItem v-bind:task="taskSelected"/>
  </div>
</template>

<script>
import TasksList from "@/components/tasks-list";
import NameCompany from "@/components/name-company";
import AddTaskItem from "@/components/add-task-item";
import EditTaskItem from "@/components/edit-task-item";
export default {
  name: 'App',
  components: {
    EditTaskItem,
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
      company: 'dix Agro',
      taskSelected:         {
        id:3,
        title: 'Study Vue Framework 3',
        completed: false
      }
    }
  },
  methods:{
    addTask(newTask){
      this.tasks = [...this.tasks, newTask] // el metodo recibe la tarea y la agrega al array
    },
    deleteTask(taskId){
      this.tasks = this.tasks.filter(task => task.id !== taskId);
    },
    editTask(taskId){
      this.taskSelected = this.tasks.find(task=> task.id === taskId )
      console.log('editing ' + taskId);
    }
  }
}
</script>

<style>
</style>
