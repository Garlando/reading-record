<template>
  <div id="app">
    <NavBar/>
    <Header/>
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
import NavBar from './components/NavBar.vue'
import Header from './components/Header.vue'
import Bookshelf from './components/Bookshelf.vue'

export default {
  name: 'App',
  components: {
    NavBar,
    Header,
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
