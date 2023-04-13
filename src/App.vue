<template>
  <div class="app" ref="app-container">
    <div class="main-container">
      <div class="filters">
        <div class="filter-heading">Filters</div>
        <ProductFilters
          @checkbox-change="updateStockFilter"
          @brand-checkbox-change="updateBrandFilter"
        />
      </div>
      <div class="product-column">
        <div class="product-count">{{ productCount }} products</div>
        <div class="product-grid">
          <ProductGrid :products="productList" />
        </div>
      </div>
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
      filters: {
        inStockFilterOn: false,
        brand: {
          nike: false,
        },
      },
    };
  },
  computed: {
    productList() {
      let updatedProductList = this.filteredProducts();
      return updatedProductList;
    },
    productCount() {
      return this.productList.length;
    },
  },
  methods: {
    filteredProducts() {
      let filteredProductList = this.products;

      return filteredProductList
        .filter((product) => this.stockFilter(product))
        .filter((product) => this.brandFilter(product));
    },
    updateStockFilter(value) {
      this.filters.inStockFilterOn = value;
    },
    updateBrandFilter(value) {
      this.filters.brand.nike = value;
    },
    stockFilter(product) {
      // Return true if in stock filter is false or product is in stock.
      return !this.filters.inStockFilterOn || product.isAvailable;
    },
    brandFilter(product) {
      // Return true if brand filter is false or product brand is Nike.
      return !this.filters.brand.nike || product.brand == 'Nike';
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

<style scoped>
.filter-heading {
  font-weight: bold;
  color: black;
  margin-bottom: 16px;
}
.main-container {
  box-sizing: border-box;
  display: flex;
  flex-direction: row;
}
.product-column {
  display: flex;
  flex-direction: column;
  width: 85%;
}
.product-count {
  padding-left: 6px;
}
.product-grid {
  display: flex;
  flex-grow: 1;
}
.filters {
  width: 15%;
  margin-right: 12px;
}
</style>
