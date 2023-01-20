<template>
  <div id="app">
    <h1>Todos</h1>
    <todo-form />
    <todos-list />
  </div>
</template>

<script>
import TodosList from "./components/TodosList";
import TodoForm from "./components/TodoForm";

export default {
  name: "app",
  components: {
    TodosList,
    TodoForm
  },
};
</script>
<style scoped>
@import './main.css'
</style>