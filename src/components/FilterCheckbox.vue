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
