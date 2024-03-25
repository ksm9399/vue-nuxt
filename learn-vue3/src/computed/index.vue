<template>
  <div>
    <h2>{{ teacher.name }}</h2>
    <h3>강의가 있습니까?</h3>
    <!-- <p> {{ teacher.lectures.length > 0 ? '있음' : '없음' }}</p> -->
    <p> {{ hasLectures }}</p>
    <p> {{ hasLectures }}</p>
    <p> {{ hasLectures }}</p>
    <p> {{ existLectures() }}</p>
    <p> {{ existLectures() }}</p>
    <p> {{ existLectures() }}</p>
    <button @click="count++">counter: {{ count }}</button>
    <h3>이름</h3>
    <p>{{ fullName }}</p>
  </div>
</template>

<script setup>
import { reactive, computed, ref } from 'vue'
  const teacher =  reactive({
    name: '짐코딩',
    lectures: [
      'HTML/CSS',
      'JavaScript',
      'vue3'
    ]
  })

  const hasLectures = computed(() => {
    console.log('computed')
    return teacher.lectures.length > 0 ? '있음' : '없음'
  })

  const existLectures = () => {
    console.log('method')
    return teacher.lectures.length > 0 ? '있음' : '없음'
  }

  const count = ref(0)

  const firstName = ref('홍')
  const lastName = ref('길동')
  const fullName = computed({
    get() {
      return `${firstName.value} ${lastName.value}`
    },
    set(value) {
      [firstName.value, lastName.value] = value.split(' ')
    }
  })
  console.log('콘솔 확인 : ', fullName.value)
  fullName.value = 'k sm'

</script>

<style lang="scss" scoped>

</style>