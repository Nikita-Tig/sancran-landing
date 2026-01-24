<script setup lang="ts">
import ContactButton from './ContactButton.vue'
</script>

<template>
  <div class="item">
    <div class="description">
      <h1>
        <slot name="heading"></slot>
      </h1>
      <slot></slot>
      <ContactButton>Связатся</ContactButton>
    </div>
  </div>
</template>

<style>
.item {
  width: 100%;
  height: 660px;
  padding: 48px 12px 12px 0;
  background: #666;
}

.description {
  display: flex;
  flex-direction: column;
  gap: 20px;
  width: 30%;
  min-width: 520px;
  background: var(--color-background-soft);
  padding: 12px 12px 12px 72px;
}

h1 {
  font: var(--font-h1);
}

p {
  font: var(--font-h4);
}

li {
  font: var(--font-body);
}
</style>
