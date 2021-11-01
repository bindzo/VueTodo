<template>
  <li class="item" @click="removeTodo(id)">{{content}} [x]</li>
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
