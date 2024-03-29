<template>
  <div>
    <h3>뷰 컴포넌트</h3>
  </div>
  <div>
    <p>The View안의 앱카드 컴포넌트</p>
    <div>
      <AppCard title="제목1" contents="내용1" />
    </div>
    <div>
      <AppCard :title="post.title" :contents="post.contents"/>
    </div>
    <div v-for="post in posts" :key="post.id">
      <AppCard :title="post.title" :contents="post.contents"/>
    </div>
    <div>
      <p>이벤트로 프롭스 값 app.vue에서 넘겨봄 </p>
      <h1>{{ props.likeFlg }}</h1>
    </div>
  </div>
  <div>
    <button @click="childClick">자식 컴포넌트 TheView에서 프롭스로전달 받은 likeFlg값 변경</button>
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import AppCard from './AppCard.vue'

const props = defineProps(['likeFlg'])
const emit = defineEmits(["childClick"])

const childClick = () => {
  console.log(`childClike fnc ${props.likeFlg}`)
  emit('childClick', props.likeFlg)
}

const post = reactive({
  title: '제목2',
  contents: '내용2'
})

const posts = reactive([
  {id: 1, title: 'arr제목3', contents: 'arr내용3'},
  {id: 2, title: 'arr제목4', contents: 'arr내용4'},
  {id: 3, title: 'arr제목5', contents: 'arr내용5'},
  {id: 4, title: 'arr제목6', contents: 'arr내용6'},
  {id: 5, title: 'arr제목7', contents: 'arr내용7'},
])


</script>

<style lang="scss" scoped>

</style>