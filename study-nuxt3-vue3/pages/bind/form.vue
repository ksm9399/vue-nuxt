<template>
  <div>
    <h3>
      <a href="https://ko.vuejs.org/tutorial/#step-4" target="_blank" rel="noopener noreferrer">
        폼(form) 바인딩
      </a>
    </h3>
    <!--
      v-bind와 v-on을 함께 사용하면, 폼 안의 입력 엘리먼트에 양방향 바인딩을 만들 수 있음
      v-model = v-bind + v-on을 합친 단축 표기법
    -->

    <!--
      가이드 - 폼(form) 입력 바인딩
        - https://ko.vuejs.org/guide/essentials/forms
    -->

    <!--
      v-model을 대신 사용하도록 코드를 리팩토링
    -->
    <div>
      <input v-model="text" placeholder="여기에 입력하기">
      <p>{{ text }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const text = ref('')
function onInput(e) {
  text.value = e.target.value
}
</script>

<style>
  p{
    border: 1px solid black;
  }
</style>