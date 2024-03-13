<template>
  <div>
    <h3>
      <a href="https://ko.vuejs.org/tutorial/#step-3" target="_blank" rel="noopener noreferrer">
        속성 바인딩
      </a>
    </h3>

    <!--
      템플릿 문법
        - https://ko.vuejs.org/guide/essentials/template-syntax
    -->

    <!--
      v-bind = :element
      ( <ex>
        v-bing:id = :id
        v-bind:class = :class
        ...등으로 단축문법 가능
      )
    -->

    <!--
      ref의 titleClass을 값으로 사용하여, <h1>의 class에 동적 바인딩을 추가해 봅시다.
      올바르게 바인딩된 경우, 텍스트가 빨간색으로 변해야 합니다.
    -->
    <h1 :class="titleClass">나를 빨갛게 만들어 보세요</h1>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const titleClass = ref('title')
</script>

<style>
.title {
  color: red;
}
</style>