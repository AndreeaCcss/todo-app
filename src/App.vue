<template>
  <div id="app">
    <Header />
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/layout/Header";

export default {
  name: "app",
  components: { Header, Todos },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "brush dog",
          completed: false
        },
        {
          id: 2,
          title: "brush cat",
          completed: false
        },
        {
          id: 3,
          title: "brush teeth",
          completed: true
        }
      ]
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  line-height: 1.5;
}
</style>
