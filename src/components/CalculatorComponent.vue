<template>
    <div class="container">
      <operation-selector v-model:selectedOperation="selectedOperation"></operation-selector>
      <input-fields v-model:number1="number1" v-model:number2="number2"></input-fields>
      <button class="btn btn-primary mt-3" @click="calculate">Calculate</button>
      <result-display :result="result" :errorMessage="errorMessage"></result-display>
    </div>
  </template>
  
  <script>
  import OperationSelector from './OperationSelector.vue';
  import InputFields from './InputFields.vue';
  import ResultDisplay from './ResultDisplay.vue';
  
  export default {
    components: {
      OperationSelector,
      InputFields,
      ResultDisplay
    },
    data() {
      return {
        selectedOperation: 'add',
        number1: null,
        number2: null,
        result: null,
        errorMessage: ''
      };
    },
    methods: {
      calculate() {
        if (this.number1 === null || this.number2 === null) {
          this.errorMessage = 'Please enter both numbers.';
          this.result = null;
          return;
        }
  
        switch (this.selectedOperation) {
          case 'add':
            this.result = this.number1 + this.number2;
            break;
          case 'subtract':
            this.result = this.number1 - this.number2;
            break;
          case 'multiply':
            this.result = this.number1 * this.number2;
            break;
          case 'divide':
            if (this.number2 === 0) {
              this.errorMessage = 'Cannot divide by zero.';
              this.result = null;
              return;
            }
            this.result = this.number1 / this.number2;
            break;
          default:
            this.errorMessage = 'Invalid operation selected.';
            this.result = null;
            return;
        }
  
        this.errorMessage = '';
      }
    }
  };
  </script>
  