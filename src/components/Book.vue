<template>
  <div v-bind:BookAttributes="BookAttributes">
      <h1>{{BookAttributes.title}}</h1>
      <h2>Finished Reading:</h2>
  </div>
</template>

<script>
export default {
    name: 'Book',
    props: ['BookAttributes']
}
</script>

<style>

</style>