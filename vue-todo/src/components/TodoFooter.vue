<template>
  <div>
    <span v-on:click="clearTodo">
      Clear All
    </span>
  </div>
</template>

<script>
export default {
  methods: {
    clearTodo(){
      localStorage.clear()
    }
  }
}
</script>

<style scoped>

</style>
