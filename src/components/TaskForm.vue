<template>
  <div class="form-container">
  <h2>Add a new Todo below</h2>
    <form class="form" @submit="addTask">
      <div class="title">
        <input type="text" placeholder="Title" v-model="title" />
      </div>
      <div class="text">
        <textarea type="text" placeholder="What to do..." v-model="text"></textarea>
      </div>
      <div class="btn">
        <button type="submit">Add Todo</button>
      </div>
    </form>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "TaskForm",
  setup() {
    const title = ref("");
    const text = ref("");

    const addTask = (e) => {
      e.preventDefault();
      const todo = { title: title.value, text: text.value };
      window.localStorage.setItem(todo.title, JSON.stringify(todo));
      window.location.reload();
    };

    return {
      addTask,
      title,
      text,
    };
  },
};
</script>

<style>
.form-container {
  display: flex;
  flex-direction: column;
  border: solid black 2px;
  border-radius: 8%;
  padding: 2rem;
  margin: 1rem;
}

.form {
  display: flex;
  flex-direction: column;
}

.title {
  padding: 1rem;
}

.title input {
  width: 180px;
}

.text {
  padding: 1rem;
}

.text textarea {
  width: 180px;
  height: 100px;
}

.btn {
  padding: 1rem;
}

.btn button {
  background-color: lightgreen;
  border-radius: 8%;
  padding: .6rem;
  opacity: 0.9;
}

.btn button:hover {
  opacity: 1;
  cursor: pointer;
}
</style>
