<template>
  <div>
      <h1>Bookshelf</h1>
      <div class="flex">
        <Book v-bind:BookAttributes="books[0]"/>
        <Book v-bind:BookAttributes="books[1]"/>
        <Book v-bind:BookAttributes="books[2]"/>
        <Book v-bind:BookAttributes="books[3]"/>
        <Book v-bind:BookAttributes="books[4]"/>
        <Book v-bind:BookAttributes="books[5]"/>
        <Book v-bind:BookAttributes="books[6]"/>
        <Book v-bind:BookAttributes="books[7]"/>
        <Book v-bind:BookAttributes="books[8]"/>
        <Book v-bind:BookAttributes="books[9]"/>
        <Book v-bind:BookAttributes="books[10]"/>
      </div>
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
                {title: "A Watermelon, A Fish And A Bible", author: "Christy Lefteri", finishedReading: "01/01/2021"},
                {title: "Time Out", author: "Emma Murray", finishedReading: "02/02/2021"},
                {author: "Lisa Jewell", title: "The Family Upstairs"},
                {author: "Clare Clark", title: "In The Full Light Of The Sun"},
                {author: "Hanna Jameson", title: "The Last"},
                {author: "Ben Aaronovitch", title: "Rivers Of London"}, 
                {author: "Curtis Sittenfeld", title: "Sisterland"},
                {author: "Ben Aaronovitch", title: "Moon Over Soho"},
                {author: "Ben Aaronovitch", title: "Whispers Underground"},
                {author: "Ben Aaronovitch", title: "Broken Homes"}
            ]
        }
    }

}
</script>

<style>

</style>