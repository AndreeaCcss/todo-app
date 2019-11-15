<template>
  <div id="app">
    <Todos v-bind:todos="todos" />
  </div>
</template>

<script>
import Todos from "./components/Todos";

export default {
  name: "app",
  components: { Todos },
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
