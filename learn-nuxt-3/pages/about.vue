<template>
  <q-page padding>
    <div class="q-my-xl text-center">
      <div class="text-h4">About</div>
      <p class="q-mt-sm text-grey-8">
        Vue & Nuxt Mastery Class 웹은 Nuxt3로 만들어졌습니다.
      </p>
      <div class="column">
        <RouterLink to="/">Route Link Home</RouterLink>
        <RouterLink to="https://youtube.com/@gymcoding">
          Route Link Youtube
        </RouterLink>
        <br />
        <NuxtLink prefetched-class="bg-yellow" :prefetch="false" to="/"
          >NuxtLink Link Home</NuxtLink
        >
        <NuxtLink to="https://youtube.com/@gymcoding">
          NuxtLink Link Youtube
        </NuxtLink>
      </div>
    </div>
  </q-page>
</template>

<script setup lang="ts">
import type { RouterLink } from 'vue-router';
</script>
