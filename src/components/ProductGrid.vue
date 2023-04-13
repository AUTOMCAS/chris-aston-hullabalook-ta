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
