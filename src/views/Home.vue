<template>
  <div class="home">
    <h1 class="home__title">Todo List in Vue.js</h1>
    <TodoList :todos="todos" @todo-toggle="toggleTodoDone" @delete-todo="deleteTodo"/>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";
import TodoList from "@/components/TodoList.vue";

export default {
  name: "Home",
  components: {
    TodoList,
    // HelloWorld,
  },
  data() {
    return {
      todos: [
        {id: 1, text: "Buy grocery", done: true},
        {id: 2, text: "Wash the car", done: false},
        {id: 3, text: "Learn programming", done: false},
      ]
    }
  },
  methods: {
    toggleTodoDone(id){
      this.todos = this.todos.map((todo) => (todo.id === id) ? {...todo, done: !todo.done} : todo)
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
    }
  }
};
</script>

<style scoped>
  .home {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .home__title {
    margin-bottom: 25px;
  }
</style>