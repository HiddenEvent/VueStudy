<template>
  <div>
    <ul>
      <li v-for="(todoItem, index) in propsdata" v-bind:key="todoItem.item">
        <i class="fas fa-check" v-on:click="toggleComplate(todoItem, index)"></i>

        <span v-bind:class="{textCompleted: todoItem.completed}">{{ todoItem.item }}</span>
        <span v-on:click="removeTodo(todoItem, index)">
         <i class="fas fa-trash-alt"></i>
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['propsdata'],
  methods: {
    removeTodo(todoItem, index) {
      this.$emit('removeItem', todoItem, index)
    },
    toggleComplate(todoItem, index){
      this.$emit('toggleItem', todoItem, index)
    }
  }
}
</script>

<style scoped>

</style>
