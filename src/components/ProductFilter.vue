<template>
    <div>
      <input type="text" v-model="filter" @input="onFilterChange" placeholder="Search products..." />
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        filter: ''
      };
    },
    methods: {
      onFilterChange() {
        this.$emit('filter', this.filter);
      }
    }
  };
  </script>
  