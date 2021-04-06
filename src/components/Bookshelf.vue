<template>
  <div>
      <h1>Bookshelf</h1>
      <div class="flex">
        <Book v-for="book in books2021" :key="book" v-bind:BookAttributes="book"/>
      </div>
      <div class="h-10 w-full bg-yellow-900"></div>
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
            ],
            books2021: require("@/resources/books_2021.json")
        }
    },
    methods: {
        getSomeBooks() {
            console.log(this.books2021)
        }
    }
}
</script>

<style>

</style>