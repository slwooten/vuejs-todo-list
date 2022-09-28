<template>
  <div class="app">
    <div class="app-container">
      <HomePage />
    </div>
  </div>
</template>

<script>
import HomePage from "./components/HomePage";

export default {
  name: "App",
  components: {
    HomePage,
  },
};
</script>

<style>
.app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.app-container {
  border: dotted black 2px;
  border-radius: 8%;
  flex: 1 1 800px;
  max-width: 800px;
  padding: 3rem;
}
</style>
