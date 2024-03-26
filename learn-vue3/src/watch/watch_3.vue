<template>
  <div>
    {{ message }}
    {{ reverseMessage }}
  </div>
</template>

<script setup>
import { ref, watch } from 'vue';

const message = ref('hello vue3')
const reverseMessage = ref('')

// watch(message, (newValue) => {
//   console.log(`immediate옵션으로 즉시실행됨`)
//   reverseMessage.value = newValue.split('').reverse().join('')
// },
// {immediate: true}
// )

const reverseFnc = () => {
  console.log(`reverseFnc실행으로 즉시 실행`)
  reverseMessage.value = message.value.split('').reverse().join('')
}
watch(message, reverseFnc)  // watch - 뭔가 반응형 데이터의 변경이 일어날때 추가적으로 api호출 및 push, route등 액션이 더 필요한 경우 적합
reverseFnc()

</script>

<style lang="scss" scoped></style>