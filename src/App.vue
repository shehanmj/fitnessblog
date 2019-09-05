<template>
  <div id="app">
    <img src="./assets/ks.jpg">
    <HelloWorld :msg="msg" />
    <Admin v-if="loggedIn" />
    <b-button v-if="!loggedIn" variant="primary" v-on:click="login(true)">login</b-button>
    <b-button v-if="loggedIn" variant="success" v-on:click="login(false)">logout</b-button>

  </div>
</template>

<script>

import HelloWorld from './components/HelloWorld.vue'
import Admin from './components/Admin.vue'
export default {
  
  name: 'app',
  components: {
    HelloWorld,
    Admin
  },
  data() {
    return {
      loggedIn: false,
      msg: this.loggedIn ? "Welcome Kim" : "Welcome to Kim's blog",
    }
  },
  methods: {
      login: function (bool) {
        this.loggedIn = bool
        this.msg = this.loggedIn ? "Welcome Kim" : "Welcome to Kim's Blog"
      }
  }
 
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
