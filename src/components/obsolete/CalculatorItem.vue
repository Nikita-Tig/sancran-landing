<script setup lang="ts">
import { ref } from 'vue'

const charSize = 540
const step = 30

for (let i = 0; i < charSize; i = i + step) {
  nums.push({ num: 2 })
}

const numbers = ref(nums)
</script>

<template>
  <div class="item">
    <div class="char">
      <ul class="bottom-numbers numbers">
        <li v-for="number in numbers" :key="number.num">
          {{ number.num }}
        </li>
      </ul>
      <ul class="side-numbers numbers">
        <li v-for="number in numbers" :key="number.num">
          {{ number.num }}
        </li>
      </ul>
    </div>
    <div class="description">
      <div class="details">
        <h3>
          <slot name="heading"></slot>
        </h3>
        <slot></slot>
        <p class="note">
          <slot name="note"></slot>
        </p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.item {
  display: flex;
  justify-content: space-between;
  background-color: gray;
}

.char {
  position: relative;
  margin: 48px 0 48px 48px;
  width: 541px;
  height: 541px;
  background-image:
    repeating-linear-gradient(var(--color-text) 0, transparent 1px, transparent 30px),
    repeating-linear-gradient(90deg, var(--color-text) 0, transparent 1px, transparent 30px);
}

.char::after {
  content: '';
  position: absolute;
}

.numbers {
  position: absolute;
  list-style: none;
  padding: 0;
  display: flex;
  font: var(--font-caption);
}

.numbers li {
  width: 9px;
  height: 26px;
}

.bottom-numbers {
  gap: 21px;
  top: 100%;
  left: -4px;
}

.side-numbers {
  flex-direction: column-reverse;
  left: 100%;
  bottom: -12px;
  gap: 4px;
}

.description {
  width: 50%;
  display: flex;
  flex-direction: column;
  gap: 40px;
  background: linear-gradient(
    275deg,
    var(--color-background-soft) 85%,
    var(--color-separator) 86%,
    transparent 90%
  );
  padding: 48px 48px 12px 100px;
}

h3 {
  font: var(--font-h2);
}

.note {
  font: var(--font-caption);
}

.calculator {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.field {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

input {
  border: none;
  border-radius: 0;
}
</style>
