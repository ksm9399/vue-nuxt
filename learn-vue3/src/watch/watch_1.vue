<template>
  <div>
    <h3>watch</h3>

  </div>
</template>

<script setup>
import { ref, watch } from 'vue';

  const message = ref('')

  watch(message, (newValue, oldeValue) => {
    console.log('newValue = ', newValue)
    console.log('oldeValue = ', oldeValue)
  })
</script>

<style lang="scss" scoped>

</style>