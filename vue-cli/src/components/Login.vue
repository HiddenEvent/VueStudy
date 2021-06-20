<template lang="">
  <form v-on:submit.prevent="submitForm">
    <div>
      <label for="username">id: </label>
      <input
        type="text"
        id="username"
        v-on:change="changeVal"
        v-model="username"
      />
    </div>
    <div>
      <label for="password">pw: </label>
      <input
        type="password"
        id="password"
        v-on:change="changeVal"
        v-model="password"
      />
    </div>
    <button>login</button>
  </form>
</template>
<script>
import axios from 'axios';

export default {
  data() {
    return {
      username: '',
      password: '',
    };
  },
  methods: {
    submitForm: function() {
      console.log(this.username, this.password);
      var url = 'https://jsonplaceholder.typicode.com/users';
      var data = {
        username: this.username,
        password: this.password,
      };
      axios
        .post(url, data)
        .then(function(response) {
          console.log(response);
        })
        .catch(function(error) {
          console.log(error);
        });
    },
    changeVal(e) {
      console.log(e.target.name);
      console.log(e.target.value);
    },
  },
};
</script>
