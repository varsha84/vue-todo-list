<template>
    <div class="container">
    <Header title="Task Tracker" ></Header>
    <Tasks @delete-task="deleteTask" :tasks="tasks"></Tasks>

    </div>
</template>

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'

export default {
  name: 'App',
    components: {
      Header,
      Tasks,
    },
  data(){
    return{
      tasks:[],
    }
  },
  methods:{
    deleteTask(id){
      console.log('task',id)
      this.tasks = this.tasks.filter((task)=>task.id !== id)
    }
  },
  created(){

    this.tasks= [{
      id: 1,
      text:'Doctors appointment',
      day:'March 1st at 2:30',
      reminder: true,
    },
    {
      id: 2,
      text:'meeting at school',
      day:'march 3rd at 1:30 am',
      reminder: true,
    
    
    },
    {
      id: 3,
      text:'dinner at royal palace',
      day:'april 4th at 2:30 am',
      reminder: false,
    },
    
  ]
  }
  
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>