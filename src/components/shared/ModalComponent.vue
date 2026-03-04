<script setup lang="ts">
const emit = defineEmits(['close'])
</script>

<template>
  <div class="overlay" @click="emit('close')">
    <div class="modal" @click.stop>
      <slot></slot>
      <button @click="emit('close')" class="button">Закрыть</button>
    </div>
  </div>
</template>

<style scoped>
.overlay {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: rgba(0, 0, 0, 0.7);
  position: fixed;
  width: 100vw;
  height: 100vh;
  top: 0;
  left: 0;
  z-index: 2;
}

.modal {
  display: flex;
  flex-direction: column;
  background-color: var(--color-background);
  gap: 20px;
  padding: 32px;
}

.button {
  margin-top: 20px;
  width: 300px;
  border: none;
  border-radius: 0;
  padding: 10px 5px;
}
</style>
