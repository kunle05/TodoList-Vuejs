<template>
  <div class="container pb-5">
    <h2 class="display-4 my-5">My Todo List</h2>
    <div class="row">
      <addTodo :add-item="addToList" />
      <todos
        :todo-list="todoList"
        :remove-todo="removeTodo"
        :completed="completeTodo"
      />
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    todoList: [],
  }),
  methods: {
    addToList(item) {
      this.todoList.push({
        todo: item,
        completed: false,
      })
    },
    removeTodo(todo) {
      this.todoList.splice(this.todoList.indexOf(todo), 1)
    },
    completeTodo(todo) {
      const currentStat = this.todoList[this.todoList.indexOf(todo)].completed
      this.todoList[this.todoList.indexOf(todo)].completed = !currentStat
    },
  },
}
</script>
