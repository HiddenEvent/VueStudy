<template>
  <div>
    <input type="text" v-model="newTodoItem" v-on:keyup.enter="addTodo">
    <button v-on:click="addTodo">add</button>
  </div>
</template>

<script>
export default {
  data: function (){
    return  {
      newTodoItem: ""
    }
  },
  methods: {
    addTodo: function (){
      if(this.newTodoItem){
        this.$emit('addTodoItem', this.newTodoItem)
        // 초기화
        this.clearInput()
      }
    },
    clearInput: function () {
      this.newTodoItem = '';
    }
  }
}
</script>

<style scoped>

</style>
