<template>
  <div class="q-pa-md">
    <div class="q-my-xl text-center q-gutter-md">
      <q-btn
        label="default layout"
        color="dark"
        @click="changePageLayout('default')"
      />
      <q-btn
        label="admin layout"
        color="primary"
        @click="changePageLayout('admin')"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import type { LayoutKey } from '#build/types/layouts';

const changePageLayout = (layout: LayoutKey) => {
  setPageLayout(layout); // 레이아웃 명을 넣으면 동적으로 변환 가능 - setPageLayout() = Nuxt제공 utils
};

definePageMeta({
  layout: false,
});
</script>

<style scoped></style>
