<template>
  <q-page padding>
    <TodoForm />
    <TodoList />
  </q-page>
</template>

<script>
import TodoForm from "../components/TodoForm.vue";
import TodoList from "../components/TodoList.vue";
import { defineComponent } from "vue";
export default defineComponent({
  name: "IndexPage",
  components: {
    TodoForm,
    TodoList,
  },
});
</script>
