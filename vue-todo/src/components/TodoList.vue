<template>
  <div>
    <ul>
      <li v-for="(todoItem, index) in todoItems" v-bind:key="todoItem.item">
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
  data() {
    return {
      todoItems: []
    }
  },
  methods: {
    removeTodo(todoItem, index) {
      console.log(todoItem, index)
      localStorage.removeItem(todoItem)
      this.todoItems.splice(index, 1);
    },
    toggleComplate(todoItem, index){
      todoItem.completed = !todoItem.completed;

      /* 로컬 storege 갱신*/
      localStorage.removeItem(todoItem.item)
      localStorage.setItem(todoItem.item, JSON.stringify(todoItem))
    }
  },
  created() {
    if (localStorage.length > 0) {
      for (let i = 0; i < localStorage.length; i++) {
        if (localStorage.key(i) !== 'loglevel:webpack-dev-server') {
          this.todoItems.push(JSON.parse(localStorage.getItem(localStorage.key(i))))
        }
      }
    }
  }
}
</script>

<style scoped>

</style>
