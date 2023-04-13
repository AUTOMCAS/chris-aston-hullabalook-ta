<template>
  <div class="app" ref="app-container">


    <div class="filters">
      <h3>Filters</h3>
      <div></div>
    </div>

    <div class="product-grid">
      <ProductGridItem :product="products[0]" />
      <ProductGridItem :product="products[1]" />
    </div>
  </div>
</template>

<script>
import ProductGridItem from './components/ProductGridItem.vue';
import products from './data/products.json';

export default {
  name: 'App',
  components: {
    ProductGridItem,
  },
  data() {
    return {
      products,
    };
  },
};
</script>

<style>
.app {
  max-width: 1024px;
  margin: 0 auto;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  color: #606569;
}

.link {
  color: #3a7f71;
}
</style>
