<template>
  <div class="product-grid-item">
    <img class="product-image" :src="product.image" />
    <div class="product-info">
      <div class="product-name">{{ product.name }}</div>
      <div>{{ product.brand }}</div>
      <div>{{ product.price }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ProductGridItem',
  props: {
    product: { type: Object, required: true, default: () => ({}) },
  },
};
</script>

<style scoped>
.product-grid-item {
  background: #ddebe8;
  max-width: 150px;
}

.product-image {
  width: 100%;
}
</style>
