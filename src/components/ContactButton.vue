<template>
  <button class="button">
    <slot></slot>
  </button>
</template>

<style scoped>
.button {
  width: 300px;
  height: 72px;
  background: var(--color-background-accent);
  color: var(--color-text);
  border-radius: 24px;
  font-size: 32px;
  font: var(--font-h2);
  border: none;
}

.button:hover {
  cursor: pointer;
}
</style>
