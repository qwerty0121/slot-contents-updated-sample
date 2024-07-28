<script setup>
import { ref, provide } from 'vue'
import ParentComponent from '@/components/ParentComponent.vue'

const logs = ref([])

provide('logs', logs)
</script>

<template>
  <main>
    <ParentComponent />
    <div>
      <h2>ログ</h2>
      <ul>
        <template v-if="logs.length === 0">
          <li>ログがありません</li>
        </template>
        <template v-for="log in logs" :key="log">
          <li>{{ log }}</li>
        </template>
      </ul>
    </div>
  </main>
</template>
