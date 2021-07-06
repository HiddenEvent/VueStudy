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
      this.$emit('clearAll')
    }
  }
}
</script>

<style scoped>

</style>
