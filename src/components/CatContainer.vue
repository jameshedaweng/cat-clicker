<template>
  <div class="cat-container" v-on:click="counter += 1">
    <img class="cat-image" src="../assets/images/normal-cat.jpg">
    <span>You clicked on this cat {{ counter }} times.</span>
  </div>
</template>

<script>
  export default {
    name: 'cat-container',
    data: function() {
      return {
        counter: 0
      };
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/scss/pages/cat_container';
</style>