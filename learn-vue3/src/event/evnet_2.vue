<template>
  <div>
    <div id="modifiers">
      <div @click="clickDiv">
        DIV 영역
        <p @click="clickP">
          P 영역
          <!-- <span @click.stop="clickSpan">
            SPAN 영역
          </span> -->
          <span @click="clickSpan">
            SPAN 영역
          </span>
          <a href="https://naver.com" target="_blank" @click.prevent="clickA">a영역</a>
        </p>
      </div>
    </div>
    <button @click.once="clickDiv">한번만 이벤트 동작</button>
  </div>
</template>

<script setup>

const clickDiv = () => {
  console.log('clickDiv')
  console.log('네이버로 페이지가 이동 되었습니다.https://naver.com')
}

const clickP = () => {
  console.log('clickP')
}

const clickSpan = () => {
  console.log('clickSpan')
  alert('좋아요')
}

const clickA = () => {
  alert('clickA 이벤트')
}
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
  padding: 40px;
}

#modifiers div {
  background-color: #ccc;
}

#modifiers p {
  background-color: #999;
}

#modifiers span {
  background-color: #666;
  display: block;
}
</style>
