<template>
  <div class="app" ref="app-container">
    <div class="filters">
      <h3>Filters</h3>
      <div></div>
    </div>

    <div class="product-grid">
      <!-- <ProductGridItem :product="products[0]" />
      <ProductGridItem :product="products[1]" /> -->
      <ProductGrid :products="products" />
    </div>
  </div>
</template>

<script>
import ProductGridItem from './components/ProductGridItem.vue';
import products from './data/products.json';
import ProductGrid from './components/ProductGrid.vue';

export default {
  name: 'App',
  components: {
    ProductGridItem,
    ProductGrid,
  },
  data() {
    return {
      products,
    };
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');
.app {
  max-width: 1024px;
  margin: 0 auto;
  font-family: 'Poppins', sans-serif;
  -webkit-font-smoothing: antialiased;
  color: #606569;
  font-size: 12px;
}

.link {
  color: #3a7f71;
}
</style>
