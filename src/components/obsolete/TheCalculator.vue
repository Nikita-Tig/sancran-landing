<script setup lang="ts">
import ItemComponent from './shared/ItemComponent.vue'
</script>

<template>
  <ItemComponent class="right">
    <template #subHeading>Калькулятор</template>
    <template #default>
      <p>Возможности автокрана могут варъироватся в зависимости от расаположения машины к грузу</p>
    </template>
    <template #extra>
      <div class="calculator">
        <div class="field">
          <span>Высота (м)</span>
          <input id="height" type="numer" />
        </div>
        <div class="field">
          <span>Длинна (м)</span>
          <input id="lenght" type="nuber" />
        </div>
        <div class="field">
          <span>Максимальный вес (кг)</span>
          <input id="max-weight" type="nuber" />
        </div>
      </div>
    </template>
    <template #illustration></template>
  </ItemComponent>
</template>

<style scoped>
.calculator {
  max-width: 80%;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.field {
  display: flex;
  flex-direction: column;
}
</style>
