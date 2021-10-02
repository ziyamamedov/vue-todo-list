<template>
  <div class="about">
    <h1>Task manager app</h1>
    <p>This is a simple task manager app that I made while learning Vue.js</p>
    <p>
      In this app you can add tasks, remove them, and toggle completed tasks.
    </p>
    <p>Ziya Mamedov©</p>
  </div>
</template>

<style lang="scss" scoped>
h1 {
  margin-bottom: 20px;
}
p {
  text-align: left;

  &:not(:last-child) {
    margin-bottom: 10px;
  }
}
</style>
