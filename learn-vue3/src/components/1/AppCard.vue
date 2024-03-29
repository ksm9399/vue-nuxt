<template>
  <div>
    카드 컴포넌트
    <p>{{ props.title }}</p>
    <p>{{ props.contents }}</p>
  </div>
  <hr />
</template>

<script setup>
const props = defineProps(['title', 'contents'])

</script>

<style lang="scss" scoped>

</style>