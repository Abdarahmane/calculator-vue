<template>
    <div>
      <div v-for="operation in operations" :key="operation.value" class="form-check">
        <input
          type="radio"
          :id="operation.value"
          :value="operation.value"
          @change="$emit('update:selectedOperation', $event.target.value)"
          :checked="selectedOperation === operation.value"
          class="form-check-input"
        />
        <label class="form-check-label" :for="operation.value">{{ operation.name }}</label>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'OperationSelector',
    props: {
      selectedOperation: String,
      operations: Array
    }
  };
  </script>
  