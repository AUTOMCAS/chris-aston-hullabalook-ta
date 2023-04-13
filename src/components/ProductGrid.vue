<template>
  <div class="product-list-container">
    <div class="product-list">
      <div v-for="product in products" :key="product.id">
        <ProductGridItem :product="product" />
      </div>
    </div>
  </div>
</template>

<script>
import ProductGridItem from './ProductGridItem.vue';
export default {
  name: 'ProductGrid',
  components: {
    ProductGridItem,
  },
  props: {
    products: Array,
  },
};
</script>

<style scoped>
.product-list-container {
  display: flex;
  width: 100%;
}
.product-list {
  display: flex;
  flex-wrap: wrap;
}
</style>
