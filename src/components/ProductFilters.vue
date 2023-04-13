<template>
  <div class="filter-categories">
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
