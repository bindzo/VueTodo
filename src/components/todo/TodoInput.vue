<template>
  <form>
    <b-form-input placeholder="type to do here" v-model="todoContent"></b-form-input>
    <span class="warning" :class="{'active-warning': isWarning}">Please type somethings</span>
    <b-button variant="success" class="button" @click.stop="submitTodo">Submit</b-button>

  </form>
</template>

<script>

export default {
  data() {
    return {
      todoContent: '',
      isWarning: false
    }
  },
  inject: ['addTodo'],
  methods: {
    submitTodo() {
      if(this.todoContent !== '') {
        const todoItem = {id: (new Date()).toString(), content: this.todoContent}
        this.addTodo(todoItem)
        this.todoContent = '',
        this.isWarning=false
      } else {
        this.isWarning = true
      }
    }
  }
};
</script>

<style scoped>
.active-warning {
  display: block !important; 
  color: red;

}
.warning {
  display: none;
  color: red;
}
.label {
  margin-right: 10px;
}
.button {
  margin-top: 10px;
}
</style>
