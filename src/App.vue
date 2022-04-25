<template>
<div class="container">
   <HeaderItem title="Task Tracker" />
   <AddTask />
   <TasksItem 
   @toggle-reminder="toggleReminder"
   @delete-task="deleteTask"
   :tasks="tasks"/>
</div>
 
</template>

<script>
import HeaderItem from './components/HeaderItem'
import TasksItem from './components/TasksItem'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
    HeaderItem,
    TasksItem,
    AddTask
  },
  data() {
    return {
      tasks: []
    }
  },
  methods: {
  deleteTask(id) {
    if(confirm('Are you sure?')) {
      this.tasks = this.tasks.filter((task) => task.id 
      !== id)
      } 
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.
      reminder } : task
      )
    }
  },
  // lifecycle method
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctors Appointment',
        day: 'April 2nd at 2:00pm',
        reminder: false,
      },
      {
        id: 2,
        text: 'Meeting at School',
        day: 'May 18th at 2:00pm',
        reminder: true,
      },
      {
        id: 3,
        text: 'Interview',
        day: 'May 21st at 10:30am',
        reminder: true,
      }
    ]
  }
}
</script>

<style>

/* Global Styles */
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
  border: 1px solid rgb(98, 15, 192);
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
