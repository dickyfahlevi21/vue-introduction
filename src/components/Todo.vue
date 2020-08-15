<template>
  <div
    v-bind:class="{ 'completed': todo.completed }"
    class="cursor-pointer grid grid-flow-col grid-cols-2"
  >
    <p v-on:click="markComplete">{{ todo.title }}</p>
    <button @click="$emit('delete-todo', todo.id)" class="col-end">
      <i class="far fa-trash-alt text-red-700"></i>
    </button>
  </div>
</template>
<script>
export default {
  name: "Todo",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.completed {
  text-decoration: line-through !important;
}
.col-end {
  grid-column: end;
}
</style>