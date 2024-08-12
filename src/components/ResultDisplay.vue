<template>
  <div>
    <p v-if="errorMessage" class="text-danger">{{ errorMessage }}</p>
    <p v-else>{{ result }}</p>
  </div>
</template>

<script>
export default {
  props: ['result', 'errorMessage']
};
</script>
