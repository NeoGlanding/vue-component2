<template>
  <form @submit="addFriends">
    <input v-model="username" type="text">
    <button type="submit">Submit</button>
  </form>
  <PropsEvent @get-lower-case="clgLowerCaseUpper" v-for="(el, index) in friends" :key="index" :username="el.username" />
</template>

<script>
import PropsEvent from './components/PropsEvent.vue'

export default {
  name: 'App',
  components: {
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
      ],
      username: '',
    }
  },
  methods: {
    clgLowerCaseUpper(lower, upper) {
      console.log(lower, upper)
    },
    addFriends(e) {
      e.preventDefault()
      this.friends.push({username: this.username})
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
