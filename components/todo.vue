<template>
  <div class="border-top px-5 py-3">
    <div class="d-flex justify-content-between center">
      <div>
        <input
          v-model="item.completed"
          class="mr-2 check"
          type="checkbox"
          @click="() => completed(item)"
        />
        <span :class="{ completed: item.completed }">
          {{ item.todo }}
        </span>
      </div>
      <button
        class="btn btn-default btn-sm btn-danger"
        @click="() => deleteItem(item)"
      >
        Delete
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    todo: {
      type: Object,
      required: true,
    },
    deleteItem: {
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
      item: this.todo,
    }
  },
}
</script>

<style>
.completed {
  text-decoration: line-through;
}
.center {
  align-items: center;
  font-size: 20px;
}
.check {
  height: 18px;
  width: 18px;
  vertical-align: middle;
}
.border-top.px-5:last-child {
  border-bottom: 1px solid #dee2e6;
}
</style>
