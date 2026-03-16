<template>
  <div class="card">
    <div v-if="$slots.img" class="illustration">
      <slot name="img"></slot>
    </div>
    <div v-if="$slots.heading && $slots.default">
      <h3 v-if="$slots.heading"><slot name="heading"></slot></h3>
      <p v-if="$slots.default"><slot></slot></p>
    </div>
  </div>
</template>

<style scoped>
.card {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  min-width: 320px;
  max-width: 400px;
  height: 600px;
  padding: 24px;
  background-color: var(--color-background);
}

.illustration {
  max-width: 400px;
  contain: content;
}

h3 {
  font: var(--font-h3);
}

p {
  line-height: 1.2;
}
</style>
