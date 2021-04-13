<template>
  <div class="outerContainer flex flex-col w-16">
    <div :style="cssVars" class="heightAdjuster">
    </div>    
    <div v-on:click="showBookDetails = true"
         v-bind:BookAttributes="BookAttributes" 
         class="bg-gradient-to-b from-indigo-500 to-blue-400 border-black border relative flex-grow">
      <div class="book flex origin-bottom-left">
        <h1 class="font-bold text-lg m-3">{{BookAttributes.Title}}</h1>
        <h2 class="text-base m-3 absolute bottom-0">{{BookAttributes.Author}}</h2>
      </div>
    </div>

    <div v-if="showBookDetails" 
         class="bg-gray-500 bg-opacity-20 absolute top-0 left-0 h-full w-full z-50 flex justify-center">
        <div class="h-96 w-96 bg-blue-400 relative mt-32">
            <div v-on:click="showBookDetails = false"
                 class="bg-red-600 h-8 w-8 absolute right-4 top-4">
            </div>
            <h1 class="text-2xl mt-2">{{BookAttributes.Title}}</h1>
            <h2 class="text-lg m-2">{{BookAttributes.Author}}</h2>
            <div class="h-64 w-52 ml-20 bg-yellow-100">
                <p>Cover image should go here</p>
            </div>
            <h2 class="absolute bottom-2 ml-5">Read on: {{BookAttributes.Date_Finished}}</h2>
        </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Book',
    props: [
        'BookAttributes',
    ],
    data() {
        return {
            showBookDetails: false
        }
    },
    methods: {
        showMore: function() {
            console.log(this.showBookDetails)
            console.log(`!!!Showing details of ${this.BookAttributes.Title}`)
            this.showBookDetails = true
            console.log(this.showBookDetails)
        }
    },
    computed: {
        cssVars() {
            return {
                '--height': Math.random()*70 + 'px'
            }
        }
    }
}
</script>

<style>
    :root {
        --height: 50px /*Default, just incase*/
    }
    .outerContainer {
        height: 30rem
    }
    .heightAdjuster {
        height: var(--height);
    }
    .book {
        height: auto;
        writing-mode: vertical-lr;
        text-orientation: sideways;
    }
</style>