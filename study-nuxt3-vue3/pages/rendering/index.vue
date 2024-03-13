<template>
  <div>
    <h3>
      <a href="https://ko.vuejs.org/tutorial/#step-2" target="_blank" rel="noopener noreferrer">
        선언적 렌더링
      </a>
    </h3>
    <!--
      Composition API에서 반응형 상태를 권장하는 선언 = ref()
      reative = 배열, map, set과 같은 컬렉션 유형에서만 사용가능, 객체 자체를 반응형으로 만듬
      ref = 모든 타입의 값을 사용할 수 있음, .value속성으로 내부 값을 노출하는 객체를 생성

      반응형 기초, 심화
        - https://ko.vuejs.org/guide/essentials/reactivity-fundamentals (기초)
        - https://ko.vuejs.org/guide/extras/reactivity-in-depth (심화)
    -->

    <!--
      템플릿의 h1에 동적 텍스트 컨텐츠를 렌더링 해보자
    -->
    <h1>나를 다이나믹하게 만들어 주세요</h1>

    <h1>{{ message }}</h1>
    <p>
      숫자세기 : {{ counter.count }}
    </p>
    <h1>{{ message.split('').reverse().join('') }}</h1>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'

const counter = reactive({
  count: 0
})

console.log(counter.count)
counter.count++

const message = ref('안녕 vue!')
console.log(message.value)
message.value = '메세지를 변경합니다.'

</script>