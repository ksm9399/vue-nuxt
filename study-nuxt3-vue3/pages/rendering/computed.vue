<template>
  <div>
    <h3>
      <a href="https://ko.vuejs.org/tutorial/#step-8" target="_blank" rel="noopener noreferrer">
        계산된 속성 - computed
      </a>
    </h3>
    <!--
      계산된 속성
        - https://v3-docs.vuejs-korea.org/guide/essentials/computed.html#basic-example

      계산된 속성(computed) vs 메서드
      - 결론 : 동일한 기능을 정의할 수 있음
      - 차이점
        - computed = 캐시됨, 반응(변경)이 일어날경우에 캐시된 데이터가 불러와짐
        - 메서드 = 리랜더링이 발생할때마다 계속 실행됨
    -->

    <!--
      filteredTodos구현,  완료된 항목 숨기기 상태일 때 할 일을 체크하면 즉시 숨겨져야 됨
    -->
    <form @submit.prevent="addTodo">
      <input v-model="newTodo">
      <button>Add Todo</button>
    </form>
    <ul>
      <li v-for="todo in filteredTodos" :key="todo.id">
        <input type="checkbox" v-model="todo.done">
        <span :class="{ done: todo.done }">{{ todo.text }}</span>
        <button @click="removeTodo(todo)">X</button>
      </li>
    </ul>
    <button @click="hideCompleted = !hideCompleted">
      {{ hideCompleted ? 'Show all' : 'Hide completed' }}
    </button>

    <h3>todos의 text변경해봄</h3>
    <p>{{ todosTextUpdate }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

let id = 0

const newTodo = ref('')
const hideCompleted = ref(false)
const todos = ref([
  { id: id++, text: 'HTML 배우기', done: true },
  { id: id++, text: 'JavaScript 배우기', done: true },
  { id: id++, text: 'Vue 배우기', done: false }
])

function addTodo() {
  todos.value.push({ id: id++, text: newTodo.value, done: false })
  newTodo.value = ''
}

function removeTodo(todo) {
  todos.value = todos.value.filter((t) => t !== todo)
}

// 이해하기 쉽게 풀어서 작성 해봄
const filteredTodos = computed(() => {
  if (hideCompleted.value) {
    return todos.value.filter(item => {
      if (item.done === false) {
        return item
      }
    })
  }
  else {
    return todos.value
  }
  // return hideCompleted.value ? todos.value.filter(item => !item.done) : todos.value
})

// get, set todos의 text 변경해봄
const todosTextUpdate = computed({
  get() { // 읽기 전용
    return todos.value
  },
  set(newValue) { // 스크립트 내부에서 computed로 선언한 변수에 대해서 변경이 일어났을 경우 감지해서 set가 동작하는거 같음, 파라미터로 변경된 값이 넘어옴
    console.log('computed set newValue', newValue)
    todosTextUpdate.value[0].text = 'backend'
    todosTextUpdate.value[1].text = 'java'
    todosTextUpdate.value[2].text = 'nuxt'
  }
})

todosTextUpdate.value = 'todosTextUpdate.value값 변경'
console.log(todosTextUpdate.value)

</script>

<style scoped>
.done {
  text-decoration: line-through;
}
</style>