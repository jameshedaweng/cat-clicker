<template>
  <div id="app">
    <h1>Cat Clicker</h1>
    <div id="main-container">
      <CatContainer
        v-for="(cat, index) in cats" 
        v-bind:key="`cat-${index}`"
        v-bind:cat="cat"
      >
      </CatContainer>
    </div>
  </div>
</template>

<script>
  import CatContainer from './components/CatContainer';
  import cats from './assets/static/cats.json';
  export default {
    name: 'app',
    components: {
      CatContainer
    },
    data: function() {
      return {
        cats: cats
      }
    }
  }
</script>

<style lang="scss">
  @import './src/assets/scss/pages/index';
</style>
