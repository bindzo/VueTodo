<template>
  <b-card bg-variant="light" title="TODO List">
  <b-card-text>
   <todo-input/>
    <b-list-group class="list">
      <todo-item
        v-for="todo in todoList"
        :key="todo.id"
        :id="todo.id"
        :content="todo.content"
      />
    </b-list-group>
  </b-card-text>
</b-card>
</template>

<script>
import TodoInput from '../components/todo/TodoInput.vue';
import TodoItem from '../components/todo/TodoItem.vue';

export default {
  components: {
    TodoItem,
    TodoInput
  },
  props: ['todoList']
};
</script>

<style scoped>
ul {
  list-style: bullet;
  padding: 20px;
  max-width: 40rem;
}
.wrapper {
  border: 1px black solid;
  width: 600px;
  padding: 10px;
}

.list {
  margin-top: 20px;
}
</style>
