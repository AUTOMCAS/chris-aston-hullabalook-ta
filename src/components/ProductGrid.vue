<template>
  <div class="product-list-container">
    <ProductGridItem :product="products[0]" />
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
