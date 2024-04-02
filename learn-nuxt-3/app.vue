<template>
  <NuxtLayout>
    <!-- NuxtPage의 경우 path의 변경이 일어나면 리랜더링 -->
    <NuxtPage />

    <!-- 라우터뷰의 경우 컴포넌트가 마운트 될때 한번만 랜더링됨 -->
    <!-- <RouterView /> -->
  </NuxtLayout>
</template>

<script setup lang="ts"></script>
