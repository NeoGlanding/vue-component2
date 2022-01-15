<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <PropsEvent @get-lower-case="clgLowerCaseUpper" v-for="(el, index) in friends" :key="index" :username="el.username" />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import PropsEvent from './components/PropsEvent.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    PropsEvent
  },
  data() {
    return {
      friends: [
        {
          username: 'Wildan'
        },
        {
          username: 'Daffa'
        },
        {
          username: 'Raka'
        }
      ]
    }
  },
  methods: {
    clgLowerCaseUpper(lower, upper) {
      console.log(lower, upper)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
