<template>
  <div id="app">
    <img src="./assets/logo.png">
    <hello-world v-bind:users="users" v-on:clickUser="clickUser"></hello-world>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data () {
    return {
      users: ['juan', 'andres', 'luis', 'pedro']
    }
  },
  methods: {
    clickUser (user) {
      console.log(user)
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
