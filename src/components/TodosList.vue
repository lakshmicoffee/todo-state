<template>
  <div class="container">
    <ul>
      <li v-for="(todo, index) in todos" :key="index" :todo="todo">
        <div class="list-items">
          <p :class="{completed: todo.completed}">{{ todo.title }}</p>
          <button @click="toggleTodoStatus(todo)" class="default" :class="{status: todo.completed}"><b>Completed</b>: {{ todo.completed }} </button>
        </div>
          <button @click="removeTodo(todo)" class="delete">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
import { mapState, mapActions } from "vuex";

export default {
  props: ["todo"],
  methods: {
    ...mapActions({
      removeTodo: "deleteTodo",
      toggleTodoStatus: "toggleTodoStatus"
    })
  },
  computed: {
    ...mapState({
      todos: "todos"
    })
  }

};
</script>

<style scoped>
.completed {
  text-decoration: line-through;
}
</style>