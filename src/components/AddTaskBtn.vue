<template>
  <button @click="showTaskForm" :style="addBtnDisplay">Add Task</button>
  <TaskForm class="taskForm" :style="taskFormDisplay" />
  <button @click="hideTaskForm" :style="taskFormDisplay">Close</button>
</template>

<script>
import { ref } from 'vue';
import TaskForm from './TaskForm';

 export default {
   name: 'AddTaskBtn',
   components: {
     TaskForm,
   },
   setup() {
     const taskFormDisplay = ref('display: none');
     const addBtnDisplay = ref('');

     const showTaskForm = () => {
       taskFormDisplay.value = '';
       addBtnDisplay.value = 'display: none';
     }

     const hideTaskForm = () => {
       taskFormDisplay.value = 'display: none';
       addBtnDisplay.value = '';
     }

     return {
       showTaskForm,
       hideTaskForm,
       taskFormDisplay,
       addBtnDisplay
     }
   }
 }
</script>
