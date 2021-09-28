<template>
  <div class="todo__wrap">
    <input 
      type="checkbox" class="todo__checkbox" :checked="todo.done"
      @change="$emit('todo-done', todo.id)"
    />
    <p :class="[todo.done && 'done' , 'todo__text']">{{todo.text}}</p>
    <button class="del_btn" @click="$emit('delete-todo', todo.id)">
      Delete todo
    </button>
  </div>
</template>

<script>
export default {
  props: {
    todo: Object
  }
}
</script>

<style scoped>

  .todo__wrap {
    display: flex;
    align-items: center;
    justify-content: flex-start;
    padding: 15px 25px;
    width: 350px;
    border: 1px solid goldenrod;
    border-radius: 10px;
    margin-bottom: 15px;
  }

  .todo__wrap:last-child {
    margin-bottom: 0;
  }

  .todo__text.done {
    color: gray;
    text-decoration: line-through;
  }

  .del_btn {
    margin-left: auto;
    background: firebrick;
    color: khaki;
  }

  .todo__checkbox {
    margin-right: 10px;
  }
</style>