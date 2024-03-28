<template>
  <div>
    <div>
      컴포넌트를 호출해보자
    </div>
    <div>
      <p>Nav 컴포넌트 호출</p>
      <TheNav />
    </div>
    <div>
      <p>view 컴포넌트 호출</p>
      <TheView />
    </div>
  </div>
</template>

<script setup>
import TheNav from '@/components/TheNav.vue'
import TheView from '@/components/TheView.vue'

</script>

<style lang="scss" scoped>

</style>