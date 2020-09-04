<template>
  <div id="app">
    <h1>Todo Application</h1>
    <hr />
    <AddTodo @add-todo="addTodo" />
    <hr />
    <TodoList v-bind:todos="todos" v-on:remove-todo="removeTodo" />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import AddTodo from "@/components/AddTodo";
export default {
  name: "App",
  data() {
    return {
      todos: [
        { id: 1, title: "Bread", completed: false },
        { id: 2, title: "Butter", completed: false },
        { id: 3, title: "Milk", completed: false },
        { id: 4, title: "Chocolate", completed: false }
      ]
    };
  },
  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(t => t.id !== id);
    },
    addTodo(newTodo) {
      this.todos.push(newTodo);
    }
  },
  components: {
    TodoList,
    AddTodo
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
  width: 500px;
  margin: 60px auto 0;
}
</style>
