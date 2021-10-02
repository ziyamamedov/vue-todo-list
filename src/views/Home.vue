<template>
  <div class="home">
    <h1 class="home__title">Todo List in Vue.js</h1>
    <AddTodoForm @submit-todo="addNewTodo" />
    <p class="home__empty-list_placeholder" v-if="!todos.length">
      You don't have any tasks
    </p>
    <TodoList
      v-else
      :todos="todos"
      @todo-toggle="toggleTodoDone"
      @delete-todo="deleteTodo"
    />
  </div>
</template>

<script>
// @ is an alias to /src
import TodoList from "@/components/TodoList.vue";
import AddTodoForm from "../components/AddTodoForm.vue";

export default {
  name: "Home",
  components: {
    TodoList,
    AddTodoForm,
  },
  data() {
    return {
      todos: [
        { id: 1, text: "Learn Vue.js", done: true },
        { id: 2, text: "Learn a new programming language", done: false },
        { id: 3, text: "Strive for perfection", done: false },
      ],
    };
  },
  methods: {
    toggleTodoDone(id) {
      this.todos = this.todos.map((todo) =>
        todo.id === id ? { ...todo, done: !todo.done } : todo
      );
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    addNewTodo(todo) {
      this.todos.push(todo);
    },
  },
};
</script>

<style scoped lang="scss">
.home {
  display: flex;
  flex-direction: column;
  align-items: center;
}
.home__title {
  margin-bottom: 25px;
}
.home__empty-list_placeholder {
  font-size: 18px;
}
</style>
