<template>
  <form @submit="addFriends">
    <input v-model="username" type="text">
    <button type="submit">Submit</button>
  </form>
  <PropsEvent @delete-friends="deleteFriends" v-for="(el, index) in friends" :key="index" :username="el.username" />
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
          username: 'Ricky'
        },
        {
          username: 'Carlos'
        },
        {
          username: 'Kobe'
        }
      ],
      username: '',
    }
  },
  methods: {
    deleteFriends(username) {
      this.friends = this.friends.filter(el => el.username !== username)
    },
    addFriends(e) {
      e.preventDefault()
      this.friends.push({username: this.username})
      this.username = ''
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
