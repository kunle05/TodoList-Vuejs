<template>
  <div v-if="todos.length" class="col-6 bg-light py-3 px-0">
    <todo
      v-for="todo in todos"
      :key="todo.todo"
      :todo="todo"
      :delete-item="removeTodo"
      :completed="completed"
    />
  </div>
</template>

<script>
export default {
  props: {
    todoList: {
      type: Array,
      required: true,
    },
    removeTodo: {
      type: Function,
      required: true,
    },
    completed: {
      type: Function,
      required: true,
    },
  },
  data() {
    return {
      todos: this.todoList,
    }
  },
}
</script>
