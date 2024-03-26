<template>
  <div>
    <form @submit.prevent>
      <input type="text" v-model.lazy="title" placeholder="title">
      <textarea name="" id="" cols="30" rows="10" v-model="contents" placeholder="contents"></textarea>
      <button @click="save(title, contents)">저장</button>
    </form>
  </div>
</template>

<script setup>
import { ref, watchEffect } from 'vue';


const title = ref('')
const contents = ref('')

const save = (title, contents) => {
  console.log(`저장되었습니다. title: ${title}, contents: ${contents}`)
}

watchEffect(() => {
  console.log('watchEffect')
  console.log(title.value)
  console.log(contents.value)
  save(title.value, contents.value)
})

</script>

<style lang="scss" scoped></style>