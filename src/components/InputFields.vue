<template>
  <div>
    <input type="number" v-model="num1" placeholder="Enter first number">
    <input type="number" v-model="num2" placeholder="Enter second number">
  </div>
</template>

<script>
export default {
  props: ['number1', 'number2'],
  data() {
    return {
      num1: this.number1,
      num2: this.number2
    };
  },
  watch: {
    num1(newValue) {
      this.$emit('update:number1', newValue);
    },
    num2(newValue) {
      this.$emit('update:number2', newValue);
    }
  }
};
</script>
