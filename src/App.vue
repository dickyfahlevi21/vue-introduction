<template>
  <div id="app" class="lg:container lg:mx-auto text-center mt-10">
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo" />
  </div>
</template>

<script>
import Todos from "./components/Todos";
import AddTodo from "./components/AddTodo";

export default {
  name: "app",
  components: {
    Todos,
    AddTodo,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Contoh Item 1",
          completed: false,
        },
        {
          id: 2,
          title: "Contoh Item 2",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo(newTodoObj) {
      this.todos = [...this.todos, newTodoObj];
    },
    deleteTodo(todoId) {
      this.todos = this.todos.filter((todo) => todo.id !== todoId);
    },
  },
};
</script>
<style>
</style>