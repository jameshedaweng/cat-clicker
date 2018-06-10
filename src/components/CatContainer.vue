<template>
  <div class="cat-container" v-on:click="counter += 1">
    <img class="cat-image" v-bind:src="imagePath(cat.file)" v-bind:alt="cat.name">
    <h2>{{ cat.name }}</h2>
    <div class="cat-info">
      <span class="cat-count">{{ counter }}</span> clicks on this cat
    </div>
  </div>
</template>

<script>
  export default {
    name: 'cat-container',
    props: ['cat'],
    data: function() {
      return {
        counter: 0
      };
    },
    methods: {
      imagePath(image) {
        return require(`../assets/images/${image}`);
      }
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/scss/pages/cat_container';
</style>