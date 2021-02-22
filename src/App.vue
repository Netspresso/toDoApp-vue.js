<template>
  <div>
    <h1>Todo App</h1>
    <!-- Include Vue -->
    <toDoApp />
  </div>
</template>

<script>
import Todo from "./components/toDoApp.vue";

export default {
  components: {
    toDoApp: Todo,
  },
};
</script>
