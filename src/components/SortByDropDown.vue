<template>
  <div>
  <label>Sort by:</label>
  <select id="sort-by-price" v-model="sortByOption" @change="handleChange">
  <option value="">None</option>
  <option value="low-to-high">Low to High</option>
  <option value="high-to-low">High to Low</option>

  </div>
</template>

<script>
export default {
  name: 'SortByDropDown',
  data() {
    return {
      sortByOption: ''
    }
  },
  methods: {
    handleChange() {
      this.$emit('sort-by-change', this.sortByOption)
    }
  }
};
</script>
