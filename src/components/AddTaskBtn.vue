<template>
  <div class="add-task-container">
    <button class="add-btn" @click="showTaskForm" :style="addBtnDisplay">Add Todo</button>
    <TaskForm class="taskForm" :style="taskFormDisplay" />
    <button class="close-btn" @click="hideTaskForm" :style="taskFormDisplay">
      Close
    </button>
  </div>
</template>

<script>
import { ref } from "vue";
import TaskForm from "./TaskForm";

export default {
  name: "AddTaskBtn",
  components: {
    TaskForm,
  },
  setup() {
    const taskFormDisplay = ref("display: none");
    const addBtnDisplay = ref("");

    const showTaskForm = () => {
      taskFormDisplay.value = "";
      addBtnDisplay.value = "display: none";
    };

    const hideTaskForm = () => {
      taskFormDisplay.value = "display: none";
      addBtnDisplay.value = "";
    };

    return {
      showTaskForm,
      hideTaskForm,
      taskFormDisplay,
      addBtnDisplay,
    };
  },
};
</script>

<style>
.add-task-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 1rem;
}

.add-btn {
  padding: 0.7rem;
  border-radius: 8%;
  background-color: lightgreen;
  color: black;
  opacity: 0.9;
}

.add-btn:hover {
  opacity: 1;
  cursor: pointer;
}

.close-btn {
  padding: 0.7rem;
  border-radius: 8%;
  background-color: pink;
  color: black;
  opacity: 0.9;
}

.close-btn:hover {
  opacity: 1;
  cursor: pointer;
}

</style>
