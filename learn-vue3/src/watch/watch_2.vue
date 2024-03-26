<template>
  <div>

  </div>
</template>

<script setup>
import { reactive, ref, watch } from 'vue';

const x = ref(0)
const y = ref(0)
const obj = reactive({
  count: 0
})
// watch(() => x.value + y.value, (sum, oldValue) => {
//   console.log('sum = ', sum)
//   console.log('oldValue = ', oldValue)
// })
watch([x, y], (newX, newY) => {
  console.log(newX, newY)
})
// watch(() => obj.count, (newValue, oldValue) => {
//   console.log('newValue = ', newValue)
// })
watch(obj, (newValue, oldValue) => {
  console.log('newValue = ', newValue)
  console.log('oldValue = ', oldValue)
})

const person = reactive({
  name: '홍길동',
  age: 30,
  hobby: '운동',
  obj: {
    count: 0,
  }
})
watch(person, (newValue) => {
  console.log(newValue)
})
watch(() => person.obj, (newValue) => {
  console.log(newValue)
})
</script>

<style lang="scss" scoped>

</style>