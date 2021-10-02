<template>
  <div class="todo-list__wrapper">
    <TodoItem
      v-for="todo in todos"
      :key="todo.id"
      :todo="todo"
      @todo-done="$emit('todo-toggle', todo.id)"
      @delete-todo="$emit('delete-todo', todo.id)"
    />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";

export default {
  components: {
    TodoItem,
  },
  props: {
    todos: Array,
  },
  emits: ["todo-toggle", "delete-todo"],
};
</script>

<style lang="scss" scoped>
.todo-list__wrapper {
  width: 100%;
}
</style>
