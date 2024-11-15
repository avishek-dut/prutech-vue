<template>
    <div class="basket">
      <h2>Basket</h2>
      <div v-if="basket.length === 0">No items in basket</div>
      <ul v-else>
        <li v-for="(item, index) in basket" :key="index">
          {{ item.name }} - ${{ item.price }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: ['basket']
  };
  </script>
  
  <style scoped>
  .basket {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px;
    width: 100%;
    float: left;
  }
  </style>
  