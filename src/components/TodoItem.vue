<template>
  <div class="todo__wrap">
    <input
      type="checkbox"
      class="todo__checkbox"
      :checked="todo.done"
      @change="$emit('todo-done', todo.id)"
    />
    <p :class="[todo.done && 'done', 'todo__text']">{{ todo.text }}</p>
    <div class="todo__btn-wrap">
      <AppBtn
        text="Delete Task"
        color="red"
        @btn-click="$emit('delete-todo', todo.id)"
      />
    </div>
  </div>
</template>

<script>
import AppBtn from "./AppBtn.vue";

export default {
  components: { AppBtn },
  props: {
    todo: Object,
  },
};
</script>

<style scoped lang="scss">
.todo__wrap {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  padding: 15px 25px;
  width: 100%;
  border: 1px solid goldenrod;
  border-radius: 10px;
  margin-bottom: 15px;
}

.todo__wrap:last-child {
  margin-bottom: 0;
}

.todo__text {
  text-align: left;

  &.done {
    color: gray;
    text-decoration: line-through;
  }
}

.todo__btn-wrap {
  margin-left: auto;
  min-width: 95px;
}

.todo__checkbox {
  margin-right: 10px;
}
</style>
