<template>
  <div class="filter-categories">
    <div class="filter-heading">Availability</div>
    <FilterCheckbox
      label="In stock"
      @checkbox-change="$emit('checkbox-change', $event)"
    />
  </div>
</template>

<script>
import FilterCheckbox from './FilterCheckbox.vue';
export default {
  name: 'ProductFilters',
  components: { FilterCheckbox },
  emits: ['checkbox-change'],
  data() {
    return {
      isChecked: this.value,
    };
  },
  methods: {
    handleChange() {
      this.$emit('checkbox-change', this.isChecked);
    },
  },
};
</script>

<style scoped>
.filter-categories {
  margin-bottom: 20px;
}
.filter-heading {
  margin-bottom: 6px;
}
.label {
  cursor: pointer;
}
</style>
