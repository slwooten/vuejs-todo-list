<template>
  <div class="todo-container">
    <h2>{{ item.title }}</h2>
    <div class="description">
      <p>{{ item.text }}</p>
    </div>
    <button @click="deleteTask" :value="item.title">Remove</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["item"],
  setup() {
    const deleteTask = (e) => {
      const todo = e.target.value;

      window.localStorage.removeItem(todo);
      window.location.reload();
    };

    return {
      deleteTask,
    };
  },
};
</script>

<style>
.todo-container {
  margin: 1rem;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
  border: solid black 2px;
  border-radius: 8%;
}

.todo-container button {
  border-radius: 8%;
  padding: .5rem;
  background-color: pink;
  margin: 1rem;
  opacity: .9;
}

.todo-container button:hover {
  cursor: pointer;
  opacity: 1;
}

.description {
  padding: 1rem;
  width: 250px;
  height: 80px;
}

</style>
