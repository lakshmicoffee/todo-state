<template>
  <form>
    <input type="text" v-model="newTodoItem"
            name="TodoItems"
            autocomplete="off"
            placeholder="Enter To Do Items" />
    <button @click="addNewTodoItem()" class="add">Add</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      newTodoItem: ""
    };
  },

  methods: {
    addNewTodoItem() {
      this.$store.dispatch("addNewTodo", this.newTodoItem);
      this.newTodoItem = "";
    }
  }
};
</script>