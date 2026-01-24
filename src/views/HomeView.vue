<script setup lang="ts">
import CalculatorItem from '@/components/CalculatorItem.vue'
import TechInfoItem from '@/components/TechInfoItem.vue'
import TheHome from '@/components/TheHome.vue'
</script>

<template>
  <main>
    <TheHome />
    <CalculatorItem />
    <TechInfoItem />
  </main>
</template>

<style>
main {
  width: 100%;
  margin: 72px 0 72px;
  gap: 72px;
}
</style>
