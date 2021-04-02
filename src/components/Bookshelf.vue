<template>
  <div>
      <h1>Bookshelf</h1>
      <Book v-bind:BookAttributes="books[0]"/>
      <Book v-bind:BookAttributes="books[1]"/>
  </div>
</template>

<script>
import Book from './Book.vue';
export default {
    components: {
        Book
    },
    data() {
        return {
            books: [
                {title: "Book 1", finishedReading: "01/01/2021"},
                {title: "Book 2", finishedReading: "02/02/2021"}
            ]
        }
    }

}
</script>

<style>

</style>