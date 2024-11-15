<template>
    <div>
      <select v-model="sortOption" @change="onSortChange">
        <option value="name">Sort by Name</option>
        <option value="price">Sort by Price</option>
      </select>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        sortOption: 'name'
      };
    },
    methods: {
      onSortChange() {
        this.$emit('sort', this.sortOption);
      }
    }
  };
  </script>
  