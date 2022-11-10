<template>
  <q-form @submit.prevent="onSubmit" @reset="onReset" class="q-gutter-md">
    <div>
      <q-input filled v-model="todo" type="text" label="Type your list" />
    </div>
    <div>
      <q-btn label="Add" type="submit" color="primary" />
      <q-btn label="Reset" type="reset" color="primary" flat class="q-ml-sm" />
    </div>
  </q-form>
</template>
<script>
import { useTodoListStore } from "../stores/useTodoListStore";
export default {
  name: "TodoForm",
  data() {
    return {
      todo: "",
      store: useTodoListStore(),
    };
  },
  methods: {
    onSubmit() {
      if (this.todo.length == 0) return;
      this.store.addTodo(this.todo);
      this.todo = "";
    },
    onReset() {
      this.todo = "";
    },
  },
};
</script>
