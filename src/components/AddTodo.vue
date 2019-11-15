<template>
  <div>
    <form @submit="addTodo">
      <!-- bind title to input -->
      <input type="text" name="title" v-model="title" placeholder="Add todo" />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
// import uuid from "uuid";

export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(event) {
      event.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      };
      // send constructed object to parent
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>

<style scoped>
form {
  display: flex;
}
input[type="text"] {
  flex: 10;
  padding: 5px;
}
input[type="submit"] {
  flex: 2;
}
</style>
