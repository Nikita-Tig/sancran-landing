<script setup lang="ts">
import ItemComponent from './shared/ItemComponent.vue'
</script>

<template>
  <ItemComponent class="left">
    <template #heading>Сан Кран</template>
    <template #default>
      <p>
        Сан Кран – это молодая компания, основанная двумя братьями, которые большую часть жизни
        работали крановщиками. Часто они замечали небрежное отношение начальства к технике и
        заказам. Так появилась идея открыть собственное дело, чтобы заказы выполнялись качественно и
        в сроки.
      </p>
    </template>
    <template #illustration>
      <img src="../assets/images/cranePhotoWinter.png" alt="Crane in winter" />
    </template>
  </ItemComponent>
</template>

<style scoped>
img {
  max-height: 100%;
  max-width: 100%;
  display: inline-block;
}

@media (min-width: 1024px) {
  img {
    height: 100%;
    max-width: none;
  }
}
</style>
