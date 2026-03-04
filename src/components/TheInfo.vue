<script setup lang="ts">
import ContactButton from './shared/ContactButton.vue'
import ItemComponent from './shared/ItemComponent.vue'
</script>

<template>
  <ItemComponent class="left">
    <template #heading>Автокран 25 тонн</template>
    <template #subHeading>Основные характеристики автокрана</template>
    <template #default>
      <ul>
        <li>Вылет стрелы: 31 метров</li>
        <li>Грузоподъемность: 25 тонн</li>
        <li>Минимальное время для заказа: 4 часа</li>
      </ul>
    </template>
    <template #extra><ContactButton></ContactButton></template>
    <template #illustration>
      <img src="../assets/images/cranePhoto.png" alt="crane" />
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
    max-height: 100%;
    max-width: none;
  }
}
</style>
