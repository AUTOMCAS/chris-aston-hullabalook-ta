<template>
  <div class="app" ref="app-container">
    <div class="filters">
      <h3>Filters</h3>
      <div>
        <ProductFilters @checkbox-change="updateStockFilter" />
      </div>
    </div>

    <div class="product-grid">
      <ProductGrid :products="productList" />
    </div>
  </div>
</template>

<script>
import ProductGridItem from './components/ProductGridItem.vue';
import products from './data/products.json';
import ProductGrid from './components/ProductGrid.vue';
import ProductFilters from './components/ProductFilters.vue';

export default {
  name: 'App',
  components: {
    ProductGridItem,
    ProductGrid,
    ProductFilters,
  },
  data() {
    return {
      products,
      inStockFilterOn: false,
    };
  },
  computed: {
    productList() {
      let updatedProductList = this.filteredProducts();
      return updatedProductList;
    },
  },
  methods: {
    filteredProducts() {
      let filteredProductList = this.products;

      return filteredProductList.filter((product) => this.stockFilter(product));
    },
    updateStockFilter(value) {
      this.inStockFilterOn = value;
    },
    stockFilter(product) {
      // Return true if in stock filter is false or product is in stock.
      return !this.inStockFilterOn || product.isAvailable;
    },
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
