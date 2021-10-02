<template>
  <button :class="['app_btn', color]" @click="$emit('btn-click')">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "AppBtn",
  props: {
    text: String,
    color: String,
  },
  methods: {
    clickHandler() {
      this.onClick();
    },
  },
};
</script>

<style lang="scss" scoped>
.app_btn {
  background-color: lawngreen;
  padding: 5px 10px;
  outline: none;
  border: 1px solid black;
  border-radius: 4px;

  &.red {
    background-color: red;
    color: white;
  }
}
</style>
