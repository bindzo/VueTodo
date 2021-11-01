<template>
  <form>
    <label class="label">New to do: </label>
    <input type="text" placeholder="type to do here" v-model="todoContent">
    <span class="warning" :class="{activeWarning: this.todoContent === ''}">Please type somethings</span>
    <button type="button" @click.stop="submitTodo">Submit</button>
  </form>
</template>

<script>

export default {
  data() {
    return {
      todoContent: ''
    }
  },
  inject: ['addTodo'],
  methods: {
    submitTodo() {
      console.log(this.todoContent, this.todoContent !== '');
      if(this.todoContent !== '') {
        const todoItem = {id: (new Date()).toString(), content: this.todoContent}
        this.addTodo(todoItem)
        this.todoContent = ''
      }
    }
  }
};
</script>

<style scoped>
.active-warning {
  display: block !important; 
}
.warning {
  display: none;
  color: red;
}
.label {
  margin-right: 10px;
}
</style>
