<template>
  <div class="w-64 mx-auto">
    <ul>
      <li v-bind:key="todo.id" v-for="todo in todos">
        <Todo
          v-bind:todo="todo"
          v-on:delete-todo="$emit('delete-todo', todo.id)"
          class="flex w-full bg-gray-200 text-gray-700 border rounded py-3 px-4 mb-3"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from "./Todo";

export default {
  name: "Todos",
  components: {
    Todo,
  },
  props: ["todos"],
};
</script>

<style scoped>
.inline-block {
  display: inline-block !important;
}
</style>