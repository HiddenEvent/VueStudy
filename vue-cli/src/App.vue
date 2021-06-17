<template lang="ko">
  <div>
    <app-header></app-header>
  </div>
</template>
<script>
import AppHeader from './components/AppHeader.vue';

export default {
  data() {
    return {
      str: 'hi',
    };
  },
  components: {
    'app-header': AppHeader,
  },
};
</script>
<style lang=""></style>
