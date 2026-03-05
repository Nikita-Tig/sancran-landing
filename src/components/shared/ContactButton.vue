<script setup lang="ts">
import { inject } from 'vue'
type func = () => void
const openModal = inject<func>('openModal', () => {})
</script>

<template>
  <button @click="openModal()" class="button">Связатся</button>
</template>

<style scoped>
.button {
  padding: 8px;
  font: var(--font-h2);
}

@media (min-width: 1024px) {
  .button {
    width: 260px;
    padding: 12px;
    font: var(--font-h2);
  }
}
</style>
