<template lang="ko">
  <div>
    <app-header v-bind:propsdata="str"
    v-on:renew="renewStr"></app-header>
   <app-login></app-login>
  </div>
</template>
<script>
import AppHeader from './components/AppHeader2.vue';
import Login from './components/Login.vue';

export default {
  data() {
    return {
      str: 'Header',
    };
  },
  components: {
    'app-header': AppHeader,
    'app-login': Login,
  },
  methods: {
    renewStr() {
      this.str = 'hi';
    },
  },
};
</script>
<style lang=""></style>
