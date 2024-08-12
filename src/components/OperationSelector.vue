<template>
  <div>
    <select v-model="selected">
      <option value="add">Addition</option>
      <option value="subtract">Subtraction</option>
      <option value="multiply">Multiplication</option>
      <option value="divide">Division</option>
    </select>
  </div>
</template>

<script>
export default {
  props: ['selectedOperation'],
  data() {
    return {
      selected: this.selectedOperation
    };
  },
  watch: {
    selected(newValue) {
      this.$emit('update:selectedOperation', newValue);
    }
  }
};
</script>
