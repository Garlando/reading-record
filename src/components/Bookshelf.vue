<template>
  <div class="">
    <div class="dropdown">
      <button class="dropbtn rounded-md bg-indigo-500">Year</button>
      <div class="dropdown-content">
        <a v-on:click="selectYear('books2014')" href="#">2014</a>
        <a v-on:click="selectYear('books2015')" href="#">2015</a>
        <a v-on:click="selectYear('books2016')" href="#">2016</a>
        <a v-on:click="selectYear('books2017')" href="#">2017</a>
        <a v-on:click="selectYear('books2018')" href="#">2018</a>
        <a v-on:click="selectYear('books2019')" href="#">2019</a>
        <a v-on:click="selectYear('books2020')" href="#">2020</a>
        <a v-on:click="selectYear('books2021')" href="#">2021</a>
      </div>
    </div>
    <div class="flex w-full overflow-x-auto">
      <Book
        v-for="book in currentBooks"
        :key="book"
        v-bind:BookAttributes="book"
      />
    </div>
    <div class="h-10 w-full bg-gradient-to-b from-yellow-600 to-black"></div>
  </div>
</template>

<script>
import sortArray from "sort-array";
import moment from "moment";
import Book from "./Book.vue";
export default {
  components: {
    Book,
  },
  data() {
    return {
      books2014: require("@/resources/books_2014.json"),
      books2015: require("@/resources/books_2015.json"),
      books2016: require("@/resources/books_2016.json"),
      books2017: require("@/resources/books_2017.json"),
      books2018: require("@/resources/books_2018.json"),
      books2019: require("@/resources/books_2019.json"),
      books2020: require("@/resources/books_2020.json"),
      books2021: require("@/resources/books_2021.json"),
      currentBooks: []
    };
  },
  methods: {
    getSomeBooks() {
      console.log(this.books2021);
    },
    selectYear(year) {
        this.currentBooks = this[year]
    },
    sortBooksByDate(books) {
      sortArray(books, {
        by: "date",
        computed: {
          date: (book) => moment(book.Date_Finished, "D.M.YY"),
        },
      });
      return books;
    },
    sortBooksByAuthor(books) {
      sortArray(books, {
        by: "Author",
      });
      return books;
    },
  }
};
</script>

<style>
div::-webkit-scrollbar {
  display: none;
}

/* Dropdown Button */
.dropbtn {
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
}

/* The container <div> - needed to position the dropdown content */
.dropdown {
  position: relative;
  display: inline-block;
}

/* Dropdown Content (Hidden by Default) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

/* Change color of dropdown links on hover */
.dropdown-content a:hover {background-color: #ddd;}

/* Show the dropdown menu on hover */
.dropdown:hover .dropdown-content {display: block;}

/* Change the background color of the dropdown button when the dropdown content is shown */
/* .dropdown:hover .dropbtn {background-color: #3e8e41;} */
</style>