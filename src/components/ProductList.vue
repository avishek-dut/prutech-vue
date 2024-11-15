<template>
  <div>
    <ProductFilter @filter="applyFilter" />
    <ProductSort @sort="applySort" />

    <div v-if="filteredProducts.length === 0">No products found</div>
    <div v-else>
      <ProductItem 
        v-for="product in filteredProducts" 
        :key="product.id" 
        :product="product" 
        @add-to-basket="addToBasket" 
      />
    </div>
  </div>
</template>

<script>
import ProductItem from './ProductItem.vue';
import ProductFilter from './ProductFilter.vue';
import ProductSort from './ProductSort.vue';
import Basket from './Basket.vue';
export default {
  components: {
    ProductItem,
    ProductFilter,
    ProductSort,
    Basket
  },
  data() {
    return {
      products: [
      {"image": "https://cdn.dummyjson.com/products/images/beauty/Essence%20Mascara%20Lash%20Princess/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 100 },
        {"image": "https://cdn.dummyjson.com/products/images/beauty/Eyeshadow%20Palette%20with%20Mirror/thumbnail.png", id: 1, "title": "Powder Canister",  "category": "beauty", price: 200 },
        {"image": "https://cdn.dummyjson.com/products/images/beauty/Red%20Nail%20Polish/thumbnail.png", id: 1, "title": "Red Nail Polish",  "category": "beauty", price: 100 },
        {"image": "https://cdn.dummyjson.com/products/images/fragrances/Calvin%20Klein%20CK%20One/thumbnail.png", id: 1, "title": "Calvin Klein CK One",  "category": "beauty", price: 100 },
        {"image": "https://cdn.dummyjson.com/products/images/fragrances/Chanel%20Coco%20Noir%20Eau%20De/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 140 },
        {"image": "https://cdn.dummyjson.com/products/images/fragrances/Dior%20J'adore/thumbnail.png", id: 1, "title": "Dolce Shine Eau de",  "category": "beauty", price: 100 },
        {"image": "https://cdn.dummyjson.com/products/images/fragrances/Gucci%20Bloom%20Eau%20de/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 160 },
        {"image": "https://cdn.dummyjson.com/products/images/beauty/Essence%20Mascara%20Lash%20Princess/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 400 },
        {"image": "https://cdn.dummyjson.com/products/images/beauty/Essence%20Mascara%20Lash%20Princess/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 800 },
        {"image": "https://cdn.dummyjson.com/products/images/beauty/Essence%20Mascara%20Lash%20Princess/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 500 },
        {"image": "https://cdn.dummyjson.com/products/images/beauty/Essence%20Mascara%20Lash%20Princess/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 600 },
        {"image": "https://cdn.dummyjson.com/products/images/beauty/Essence%20Mascara%20Lash%20Princess/thumbnail.png", id: 1, "title": "Essence Mascara Lash Princess",  "category": "beauty", price: 700 },
        
      ],
      filter: '',
      sortOption: 'title'
    };
  },
  computed: {
    filteredProducts() {
      if (!this.filter) {
        return this.products;
      }
      return this.products.filter(product => 
        product.title.toLowerCase().includes(this.filter.toLowerCase())
      );
    },
    sortedProducts() {
            return this.filteredProducts.sort((a, b) => {
                if (this.sortOption === 'name') {
                    return a.title.localeCompare(b.title);
                } else if (this.sortOption === 'price') {
                    return a.price - b.price;
                }
            });
        }
        
    },
  
  methods: {
    applyFilter(filter) {
      this.filter = filter;
    },
    addToBasket(product) {
      this.basket.push(product);
    }
  }
};
</script>
