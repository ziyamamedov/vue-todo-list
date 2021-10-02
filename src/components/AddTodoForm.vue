<template>
  <form action="#" @submit.prevent="submitTodo" class="add-todo-form">
    <input
      type="text"
      name="todoTitle"
      v-model="inputValue"
      required
      class="add-todo__input"
    />
    <AppBtn text="Add Task" />
  </form>
</template>

<script>
import AppBtn from "./AppBtn.vue";

export default {
  name: "AddTodoForm",
  components: { AppBtn },
  data() {
    return {
      inputValue: "",
    };
  },
  methods: {
    submitTodo() {
      console.log(this.inputValue);
      const newTodo = { id: Math.random(), text: this.inputValue, done: false };
      this.$emit("submit-todo", newTodo);
      this.inputValue = "";
    },
  },
};
</script>

<style scoped lang="scss">
.add-todo-form {
  margin-bottom: 20px;
  width: 100%;
  display: flex;
  justify-content: space-between;
}

.add-todo__input {
  margin-right: 20px;
  padding: 10px;
  flex: 1;
}
</style>
