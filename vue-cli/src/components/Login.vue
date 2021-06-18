<template lang="">
  <form action="">
    <div>
      <label for="username">id: </label>
      <input type="text" id="username" v-model="username" />
    </div>
    <div>
      <label for="password">pw: </label>
      <input type="password" id="password" v-model="password" />
    </div>
    <button>login</button>
  </form>
</template>
<script>
export default {};
</script>
