<template>
  <div>
    <h3>
      <a href="https://ko.vuejs.org/tutorial/#step-4" target="_blank" rel="noopener noreferrer">
        이벤트 리스너
      </a>
    </h3>
    <!--
      단축 문법
        v-on:event = @event
        (
          <ex>
          v-on:click = @click
        )
    -->

    <!--
      이벤트 핸들링 가이드
        - https://ko.vuejs.org/guide/essentials/event-handling
    -->

    <!--
      increment 함수를 직접 구현하고 버튼에 이벤트를 바인딩 해보자
    -->
    <button @click="increment">숫자 세기: {{ count }}</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const count = ref(0)

const increment = () => {
  count.value++
}

</script>