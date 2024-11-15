<template>
    <div class="product-item">
      <img :src="product.image" :alt="product.name" />
      <h3>{{ product.title }}</h3>
      <p>{{ product.price | currency }}</p>
      <p>{{ product.description }}</p>
      <button @click="addToBasket">Add to Basket</button>
    </div>
  </template>
  
  <script>
  export default {
    props: ['product'],
    methods: {
      addToBasket() {
        this.$emit('add-to-basket', this.product);
      }
    },
    filters: {
      currency(value) {
        return `$${value.toFixed(2)}`;
      }
    }

    
  };
  </script>
  
  <style scoped>
  .product-item {
    border: 1px solid #ccc;
    padding: 10px;
    width: 200px;
    text-align: center;
    float: left;
    min-height: 350px;
    margin: .25rem;
  }
  .product-item img {
    width: 100%;
    height: auto;
  }
  </style>
  