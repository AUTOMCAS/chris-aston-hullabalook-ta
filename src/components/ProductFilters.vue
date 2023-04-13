<template>
  <div>
    <label class="checkbox">
      <input type="checkbox" v-model="isChecked" @change="handleChange" />
      <div class="checkbox-label">In stock</div>
    </label>
  </div>
</template>

<script>
export default {
  name: 'ProductFilters',
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
