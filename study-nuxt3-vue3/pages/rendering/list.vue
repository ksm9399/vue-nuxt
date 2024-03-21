<template>
  <div>
    <h3>
      <a href="https://ko.vuejs.org/tutorial/#step-7" target="_blank" rel="noopener noreferrer">
        리스트 랜더링
      </a>
    </h3>
    <!--
      리스트 랜더링 - 가이드
        - https://v3-docs.vuejs-korea.org/guide/essentials/list.html
    -->

    <!--
      간단한 할 일 목록, addTodo() 및 removeTodo() 메서드에 대한 로직을 구현해보기
    -->
    <form @submit.prevent="addTodo">
      <input v-model="newTodo">
      <button>할 일 추가</button>
    </form>
    <ul>
      <li v-for="todo in todos" :key="todo.id">
        {{ todo.text }}
        <button @click="removeTodo(todo)">X</button>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref } from 'vue'

// 각 할 일에 고유한 ID 부여
let id = 0

const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'HTML 배우기' },
  { id: id++, text: 'JavaScript 배우기' },
  { id: id++, text: 'Vue 배우기' }
])

function addTodo() {
  todos.value.push({id: id++, text: newTodo.value})
  newTodo.value = ''

}

function removeTodo(todo) {
  // () => , () => {}의 차이점 () => 는 결과 값을 바로 반환, () => {} 중괄호 안에 선언된 연산 로직을 수행 후 결과값 반환
  // filter() = 제공된 함수에 의해 구현된 테스트를 통과한 요소로만 필터링, 결과 배열에 요소를 유지하려면 참 값을 반환하고 그렇지 않으면 거짓 값을 반환
  todos.value =
    todos.value.filter(item => {
      if (item !== todo) return item
    })
}


</script>