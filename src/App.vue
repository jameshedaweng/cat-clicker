<template>
  <div id="app">
    <h1>Cat Clicker</h1>
    <div id="main-container">
      <CatList
        v-bind:cats="cats"
        v-bind:current_cat="current_cat"
        v-bind:setCurrentCat="setCurrentCat" 
      />
      <CatContainer
        v-bind:cat="cats[current_cat]"
        v-bind:updateCatCount="updateCatCount"
      />
    </div>
  </div>
</template>

<script>
  import CatContainer from './components/CatContainer';
  import CatList from './components/CatList';
  import cats from './assets/static/cats.json';
  export default {
    name: 'app',
    components: {
      CatList,
      CatContainer
    },
    methods: {
      setCurrentCat(index){
        this.current_cat = index;
      },
      updateCatCount(){
        this.cats[this.current_cat].count++;
      }
    },
    data() {
      return {
        cats: cats,
        current_cat: 0
      }
    },
    mounted(){
      this.cats.map(cat => cat.count = 0);
    }
  }
</script>

<style lang="scss">
  @import './src/assets/scss/pages/index';
</style>
