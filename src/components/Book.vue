<template>
  <div class="outerContainer flex flex-col w-16">
    <div :style="cssVars" class="heightAdjuster">
    </div>    
    <div v-bind:BookAttributes="BookAttributes" 
         class="bg-indigo-500 border-black border relative flex-grow">
      <div class="book flex origin-bottom-left">
        <h1 class="text-2xl m-4">{{BookAttributes.Title}}</h1>
        <h2 class="text-lg m-4 absolute bottom-0">{{BookAttributes.Author}}</h2>
      </div>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Book',
    props: ['BookAttributes'],
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
        height: 37rem
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