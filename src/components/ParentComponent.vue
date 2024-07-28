<script setup>
import { onUpdated, ref, inject } from 'vue'
import ChildComponent from '@/components/ChildComponent.vue'

const logs = inject('logs')

const count = ref(0)

onUpdated(() => {
  // 子コンポーネントに挿し込むslotコンテンツが更新されても
  // ParentComponentのupdatedはトリガーされないので、
  // この処理は実行されない
  logs.value.push(`ParentComponent updated: ${new Date()}`)
})

function onSlotContentsUpdated() {
  // slotコンテンツのupdatedはトリガーされるので、
  // この処理は実行される
  logs.value.push(`slot contents updated(Parent): ${new Date()}`)
}
</script>

<template>
  <div class="container">
    <button @click="count++">カウント</button>
    <ChildComponent>
      <span @vue:updated="onSlotContentsUpdated">テストslotコンテンツ: {{ count }}</span>
    </ChildComponent>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-flow: column nowrap;
  gap: 10px;
  align-items: center;
}
</style>
