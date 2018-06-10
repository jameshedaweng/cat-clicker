<template>
  <div class="cat-container">
    <img class="cat-image"
      v-bind:src="imagePath(cat.file)"
      v-bind:alt="cat.name"
      v-on:click="updateCurrentCount()"
    >
    <h2>{{ cat.name }}</h2>
    <div class="cat-info">
      <span class="cat-count">{{ current_count }}</span> clicks on this cat
    </div>
  </div>
</template>

<script>
  export default {
    name: 'cat-container',
    props: ['cat', 'updateCatCount'],
    methods: {
      imagePath(image) {
        return require(`../assets/images/${image}`);
      },
      updateCurrentCount() {
        this.updateCatCount();
        // Update the counter for the current cat
        this.current_count = this.cat.count;
      }
    },
    data(){
      return {
        current_count: this.cat.count || 0
      };
    },
    updated(){
      // Refresh the counter when cat changes
      this.current_count = this.cat.count;
    }
  };
</script>

<style lang="scss" scoped>
  @import '../assets/scss/pages/cat_container';
</style>