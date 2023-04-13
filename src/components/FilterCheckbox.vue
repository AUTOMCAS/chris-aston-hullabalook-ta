<template>
  <div>
    <label class="checkbox">
      <input type="checkbox" v-model="isChecked" @change="handleChange" />
      <div class="checkbox-label">{{ label }}</div>
    </label>
  </div>
</template>

<script>
export default {
  name: 'FilterCheckbox',
  data() {
    return {
      isChecked: this.value,
    };
  },
  props: {
    label: String,
  },
  methods: {
    handleChange() {
      this.$emit('checkbox-change', this.isChecked);
    },
  },
};
</script>

<style scoped>
.checkbox {
  display: flex;
  align-items: center;
}
input[type='checkbox'] {
  appearance: none;
  margin-right: 6px;
  width: 16px;
  height: 16px;
  border: 1px solid #000000;
  cursor: pointer;
}
input[type='checkbox']:checked {
  background-color: #888888;
  border: 1px solid #888888;
  padding: 6px;
}
.checkbox-label {
  font-size: 12px;
}
</style>
