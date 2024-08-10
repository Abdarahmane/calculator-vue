<template>
    <div v-if="errorMessage" class="alert alert-danger">{{ errorMessage }}</div>
    <div v-else-if="result !== null" class="alert alert-success">Result: {{ result }}</div>
  </template>
  
  <script>
  export default {
    props: ['result', 'errorMessage']
  };
  </script>
  