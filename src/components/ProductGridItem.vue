<template>
  <div class="product-grid-item">
    <img class="product-image" :src="product.image" />
    <div class="product-info">
      <div class="product-name">{{ product.name }}</div>
      <div>{{ product.brand }}</div>
      <div class="product-price">{{ `£${product.price}` }}</div>
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
  display: flex;
  flex-direction: column;
  box-sizing: border-box;
  cursor: pointer;
  padding: 6px;
}

.product-image {
  width: 100%;
  max-width: 150px;
}

.product-info {
  display: flex;
  color: #888888;
  flex-direction: column;
}

.product-price {
  font-weight: bold;
  padding-top: 3px;
}

.product-name {
  color: #000000;
  font-weight: bold;
  padding-top: 3px;
  padding-bottom: 3px;
}
</style>
