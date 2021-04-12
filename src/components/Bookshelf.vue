<template>
  <div>
      <div class="flex w-full overflow-x-auto">
        <Book v-for="book in books2021" :key="book" v-bind:BookAttributes="book"/>
      </div>
      <div class="h-10 w-full bg-yellow-900"></div>
  </div>
</template>

<script>
import sortArray from 'sort-array';
import moment from 'moment';
import Book from './Book.vue';
export default {
    components: {
        Book
    },
    data() {
        return {
            books2020: require("@/resources/books_2020.json"),
            books2021: require("@/resources/books_2021.json")
        }
    },
    methods: {
        getSomeBooks() {
            console.log(this.books2021)
        },
        sortBooksByDate(books) {
            sortArray(books,  {
                by: 'date',
                computed: {
                    date: book => moment(book.Date_Finished, "D.M.YY")
                }    
            })
            return books;
        },
        sortBooksByAuthor(books) {
            sortArray(books,  {
                by: 'Author'
            })
            return books;
        }
    }
}
</script>

<style>
    div::-webkit-scrollbar {
        display: none;
    }
</style>