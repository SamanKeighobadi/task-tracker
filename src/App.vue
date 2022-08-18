<template>
    <div class="container">
      <Header title="Task Tracker" />
      <Tasks :tasks="tasks" @delete-task="deleteTask" />
    </div>
</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks/Tasks.vue';

export default {
  name: 'App',
  components: {
    Header,
    Tasks
},
  data(){
    return{
      tasks:[]
    }
  },
  created(){
    this.tasks = [
      {
        id:1,
        text:"Go gym",
        day:"March 3rd at 1:30pm",
        reminder:true
      },
      {
        id:2,
        text:"Go gym",
        day:"March 3rd at 1:30pm",
        reminder:false
      },
      {
        id:3,
        text:"Go gym",
        day:"March 3rd at 1:30pm",
        reminder:true
      },
    ]
  },
  methods:{
    deleteTask(id){
      this.tasks = this.tasks.filter(task => task.id !== id)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  color: #2c3e50;
  margin-top: 60px;
}
</style>
