<template>
    <div>
      <label class="form-label">Enter the numbers:</label>
      <input
        type="number"
        :value="number1"
        @input="$emit('update:number1', $event.target.value)"
        class="form-control"
        placeholder="First number"
      />
      <input
        type="number"
        :value="number2"
        @input="$emit('update:number2', $event.target.value)"
        class="form-control mt-2"
        placeholder="Second number"
      />
    </div>
  </template>
  
  <script>
  export default {
    name: 'InputFields',
    props: {
      number1: Number,
      number2: Number
    }
  };
  </script>
  