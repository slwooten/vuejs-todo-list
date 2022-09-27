<template>
  <div>
    <h1>{{ item.title }}</h1>
    <h2>{{ item.text }}</h2>
    <button @click="deleteTask" :value="item.title" >X</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ['item'],
  setup() {
    const deleteTask = (e) => {
      const todo = e.target.value;

      window.localStorage.removeItem(todo);
      window.location.reload();
    }

    return {
      deleteTask,
    }
  }
};
</script>
