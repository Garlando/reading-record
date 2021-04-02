<template>
  <div class="navbar">
      <p>Annes Reading Record</p>
      <p v-on:click="click('About')" class="button">About</p>
      <p v-on:click="click('Something')" class="button">Something</p>
  </div>
</template>

<script>
export default {
    methods: {
        click: function(button) {
            console.log(button);
        }
    }
}
</script>

<style>
    .navbar {
        position: absolute;
        width: 100%;
        height: 3em;
        top: 0;
        background-color: aqua;
        display: flex;
        /* justify-content: center;
        align-items: center; */
    }
    .navbar p {
        width: 33%;
        font-size: 1rem;
        font-family: 'Courier New', Courier, monospace;
        font-weight: 600;
    }
    .button {
        height: 100%;
        margin: 0;
        line-height: 3em;
        cursor: pointer;
    }
    .button:hover {
        background-color: rgb(6, 9, 212);
        color: white;
    }
</style>