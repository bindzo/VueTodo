<template>
  <b-list-group-item button class="item" @click="removeTodo(id)">{{content}}</b-list-group-item>
</template>

<script>

export default {
  props: ['content','id'],
  inject: ['removeTodo']
};
</script>

<style scoped>
.item {
  cursor: pointer;
}
</style>
