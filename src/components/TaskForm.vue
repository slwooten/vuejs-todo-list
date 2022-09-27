<template>
  <form @submit="addTask">
    <input type="text" placeholder="Title" v-model="title">
    <textarea type="text" placeholder="What to do..." v-model="text"></textarea>
    <button type="submit">Add Task</button>
  </form>
</template>

<script>
import { ref } from 'vue';

 export default {
   name: 'TaskForm',
   setup() {
     const title = ref('');
     const text = ref('');

     const addTask = (e) => {
       e.preventDefault();
       const todo = { title: title.value, text: text.value };
       window.localStorage.setItem(todo.title, JSON.stringify(todo));
       window.location.reload();
     }

     return {
       addTask,
       title,
       text,
     }
   }
 }
</script>
