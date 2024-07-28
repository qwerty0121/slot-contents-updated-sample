<script setup>
import { onUpdated, inject } from 'vue'

const logs = inject('logs')

onUpdated(() => {
  // 自コンポーネントに差し込まれたslotコンテンツが更新された場合は
  // ChildComponentのupdatedがトリガーされるので、
  // この処理は実行される
  logs.value.push(`ChildComponent updated: ${new Date()}`)
})
</script>

<template>
  <div>
    <slot></slot>
  </div>
</template>
