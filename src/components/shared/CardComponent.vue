<template>
  <div class="card">
    <div class="illustration">
      <slot name="img"></slot>
    </div>
    <div>
      <h3><slot name="heading"></slot></h3>
      <p><slot></slot></p>
    </div>
  </div>
</template>

<style scoped>
.card {
  min-width: 320px;
  max-width: 400px;
  padding: 24px;
  background-color: var(--color-background);
}

.illustration {
  height: 350px;
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
