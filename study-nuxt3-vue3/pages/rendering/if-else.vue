<template>
  <div>
    <h3>
      <a href="https://ko.vuejs.org/tutorial/#step-6" target="_blank" rel="noopener noreferrer">
        조건부 랜더링
      </a>
    </h3>
    <!--
      v-if = true에 렌더링
      v-else = false에 렌더링
    -->

    <!--
      v-if 및 v-else 디렉티브를 추가하고 버튼을 사용하여 둘 사이를 전환할 수 있도록 toggle() 메서드를 구현
    -->
    <div>
      <button @click="toggle">토글 버튼</button>
      <h1 v-if="awesome">Vue는 굉장해! 엄청나!</h1>
      <h1 v-else>오 안돼 😢</h1>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const awesome = ref(true)

function toggle() {
  awesome.value = !awesome.value
}
</script>
