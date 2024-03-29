<template>
  <div>
    <div>
      컴포넌트를 호출해보자
    </div>
    <div>
      <p>Nav 컴포넌트 호출</p>
      <TheNav />
    </div>
    <div>
      <p>view 컴포넌트 호출</p>
      <TheView :likeFlg="likeFlg"
        @child-click="clickToggle"
      />
    </div>
    <button @click="clickToggle" >app.vue에서 토글 {{ likeFlg }}</button>
  </div>
</template>

<script setup>
import TheNav from '@/components/1/TheNav.vue'
import TheView from '@/components/1/TheView.vue'
import { ref } from 'vue';

const likeFlg = ref(true)

const clickToggle = () => {
  likeFlg.value = !likeFlg.value
}

</script>

<style lang="scss" scoped>

</style>