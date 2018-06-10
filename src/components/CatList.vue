<template>
  <div class="cat-list">
    <div
      v-for="(cat, index) in cats"
      v-bind:class="[current_cat == index? 'active': 'inactive', 'cat-list-item']"
      v-bind:key="`list-item-${index}`"
      v-on:click="setCurrentCat(index)"
    >
      {{ cat.name }}
    </div>
  </div>
</template>

<script>
  export default {
    name: 'cat-list',
    props: ['cats', 'current_cat', 'setCurrentCat']
  };
</script>

<style lang="scss" scoped>
  @import '../assets/scss/pages/cat_list';
</style>