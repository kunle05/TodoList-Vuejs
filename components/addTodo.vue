<template>
  <div class="col-6">
    <div class="form-group row">
      <div class="col-sm-7 pr-0">
        <input v-model="todo" class="form-control form-control-lg" />
      </div>
      <button class="btn btn-default btn-success col-sm-2" @click="addToList">
        Add
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    addItem: {
      type: Function,
      required: true,
    },
  },
  data: () => ({
    todo: '',
  }),
  methods: {
    addToList(e) {
      e.preventDefault()
      this.addItem(this.todo)
      this.todo = ''
    },
  },
}
</script>
