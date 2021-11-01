<template>
  <section class="container">
    <h1>TODO list</h1>
    <todo :todoList="todoList" />
  </section>
</template>

<script>
import Todo from './pages/Todo.vue';

export default {
  components: {
    Todo
  },
  provide() {
    return {
      addTodo: this.addTodo,
      removeTodo: this.removeTodo
    };
  },
  data() {
    return {
      todoList: []
    };
  },
  methods: {
    addTodo(todo) {
      const newTodoList = [...this.todoList];
      newTodoList.push(todo)
      this.todoList = newTodoList;
    },
    removeTodo(todoId) {
      const newTodoList = this.todoList.filter((todo) => todo.id !== todoId)
      this.todoList = newTodoList;
    }
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
.container {
  margin: 20px;
}
</style>
