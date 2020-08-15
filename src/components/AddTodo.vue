<template>
  <div class="flex justify-center mb-6">
    <form @submit="addTodo">
      <input
        type="text"
        v-model="title"
        name="title"
        class="shadow appearance-none border rounded-l-lg py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        placeholder="Enter Todo"
      />
      <button
        type="submit"
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-r-lg"
      >
        <i class="fas fa-plus"></i>
      </button>
    </form>
  </div>
</template>
<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodoObj = {
        title: this.title,
        completed: false,
      };
      this.$emit("add-todo", newTodoObj);
      this.title = "";
    },
  },
};
</script>

<style scoped>
</style>