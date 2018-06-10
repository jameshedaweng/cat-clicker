<template>
  <div id="app">
    <h1>Cat Clicker</h1>
    <div id="main-container">
      <CatContainer></CatContainer>
    </div>
  </div>
</template>

<script>
  import CatContainer from './components/CatContainer';

  export default {
    name: 'app',
    components: {
      CatContainer
    }
  }
</script>

<style lang="scss">
  @import './src/assets/scss/pages/index';
</style>
