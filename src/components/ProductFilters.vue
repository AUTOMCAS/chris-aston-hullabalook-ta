<template>
  <div class="filter-categories">
    <div class="filter-type-heading">Availability</div>
    <FilterCheckbox
      label="In stock"
      @checkbox-change="$emit('checkbox-change', $event)"
    />
  </div>
  <div class="filter-categories">
    <div class="filter-type-heading">Brand</div>
    <FilterCheckbox label="Nike" @checkbox-change="nikeHandler" />
  </div>
</template>

<script>
import FilterCheckbox from './FilterCheckbox.vue';
export default {
  name: 'ProductFilters',
  components: { FilterCheckbox },
  emits: ['checkbox-change', 'brand-checkbox-change'],
  data() {
    return {
      nikeChecked: false,
    };
  },
  methods: {
    nikeHandler(value) {
      this.nikeChecked = value;
      this.$emit('brand-checkbox-change', this.nikeChecked);
    },
  },
};
</script>

<style scoped>
.filter-categories {
  margin-bottom: 20px;
}
.filter-type-heading {
  color: black;
  margin-bottom: 6px;
}
.label {
  cursor: pointer;
}
</style>
