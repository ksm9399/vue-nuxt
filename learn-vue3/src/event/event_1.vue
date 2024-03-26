<template>
  <div>
    <button @click="printEventInfo('hello vue3', $event)">inline event handler</button>
    <br />
    <hr />
    <input type="text" @keyup="onKeyupHandler">
  </div>
</template>

<script setup>
const printEventInfo = (message, event) => {
  console.log('message = ', message)
  console.log('event.target = ', event.target)
  console.log('event.target.tagName = ', event.target.tagName)
}

const onKeyupHandler = (event) => {
  console.log(`event.key = ${event.key}`)
}
</script>

<style scoped></style>
