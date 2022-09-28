<template>
  <h1>My Todo List:</h1>
  <AddTaskBtn />
  <div class="todos">
    <div v-for="item in keysArr" :key="item">
      <TodoItem :item="item" />
    </div>
  </div>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import AddTaskBtn from './AddTaskBtn';
import TodoItem from './TodoItem';

 export default {
   name: 'HomePage',
   components: {
     AddTaskBtn,
     TodoItem,
   },
   setup() {
     const keys = ref([]);
     const keysArr = ref([]);

     onBeforeMount(() => {
       keys.value = Object.keys(localStorage);
       keys.value.map((key) => {
         const item = JSON.parse(window.localStorage.getItem(key));
         keysArr.value.push(item);
       })
     })

     return {
       keys,
       keysArr,
     }
   }
 }
</script>

<style>
  .todos {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
  }
</style>
