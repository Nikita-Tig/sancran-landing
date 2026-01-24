<script setup lang="ts">
import InfoItem from './InfoItem.vue'
</script>

<template>
  <InfoItem>
    <template #heading>Автокран 25 тонн</template>
    <p>Основные характеристики автокрана</p>
    <ul>
      <li>Вылет стрелы: 31 метров</li>
      <li>Грузоподъемность: 25 тонн</li>
      <li>Минимальное время для заказа: 4 часа</li>
    </ul>
    <template #img>
      <img src="" alt="" />
    </template>
  </InfoItem>
</template>
