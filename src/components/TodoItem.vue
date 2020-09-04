<template>
  <li>
    <span v-bind:class="{done: todo.completed}">
      <input type="checkbox" v-on:change="todo.completed = !todo.completed" />
      <strong>{{ index+1 }}</strong>
      {{ todo.title }}
    </span>
    <button class="remove-btn" v-on:click="$emit('remove-todo', todo.id)">&times;</button>
  </li>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true
    },
    index: Number
  }
};
</script>

<style scoped>
li {
  border: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  padding: 0.2rem 0.5rem;
  margin-bottom: 1rem;
}
.remove-btn {
  background: rgb(184, 0, 0);
  color: #fff;
  border-radius: 50%;
  font-weight: bold;
}
input {
  margin-right: 0.5rem;
}
.done {
  text-decoration: line-through;
}
</style>