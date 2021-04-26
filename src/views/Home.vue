<template>
  <div id="app">
    <div v-if="!$auth.loading">
      <button v-if="!$auth.isAuthenticated" @click="login"
        class="absolute top-5 right-10 dropbtn rounded-md bg-indigo-500">
        Log in
      </button>
      <button v-if="$auth.isAuthenticated" @click="logout"
        class="absolute top-5 right-10 dropbtn rounded-md bg-indigo-500">
        Logout
      </button>
    </div>
    <Bookshelf/>
    <div class="">
      <p class="text-lg">Things that it could do:</p>
      <ul class="list-decimal">
        <li class>Add new books</li>
        <li>Show cover art/Spine art</li>
        <li>Show statistics</li>
        <li>Sort by Title, author, date read, any other attribute</li>
        <li>Anything you want!</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bookshelf from '../components/Bookshelf.vue'

export default {
  name: 'App',
  components: {
    Bookshelf
  },
  methods: {
    login() {
      this.$auth.loginWithRedirect();
    },
    logout() {
      this.$auth.logout({
        returnTo: window.location.origin
      })
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
