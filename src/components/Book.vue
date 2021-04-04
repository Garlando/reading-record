<template>
  <div v-bind:BookAttributes="BookAttributes" class="bg-blue-400 m-2 border-black border w-auto relative">
      <div class="book flex origin-bottom-left">
        <h1 class="text-xl m-4">{{BookAttributes.title}}</h1>
        <h2 class="text-lg m-4 absolute bottom-0">{{BookAttributes.author}}</h2>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Book',
    props: ['BookAttributes']
}
</script>

<style>
    .book {
        height: 34rem;
        writing-mode: vertical-lr;
        text-orientation: sideways;
    }
</style>