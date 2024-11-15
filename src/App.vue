<template>
  <div id="app">
    <h1>Product Catalogue</h1>
    <ProductList @add-to-basket="addToBasket" />
    <Basket :basket="basket" />
  </div>
</template>

<script>
import ProductList from './components/ProductList.vue';
import Basket from './components/Basket.vue';

export default {
  components: {
    ProductList,
    Basket
  },
  data() {
    return {
      basket: []
    };
  },
  methods: {
    addToBasket(product) {
      this.basket.push(product);
    }
  }
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  margin: 20px;
  
}
</style>
