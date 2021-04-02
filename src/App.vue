<template>
  <div id="app">
    <NavBar/>
    <Bookshelf/>
  </div>
</template>

<script>
import NavBar from './components/NavBar.vue'
import Bookshelf from './components/Bookshelf.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Bookshelf
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
