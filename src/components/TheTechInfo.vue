<script setup lang="ts">
import ItemComponent from './shared/ItemComponent.vue'
</script>

<template>
  <ItemComponent class="center">
    <template #subHeading>Техничкеские характеристики [название машины]</template>
    <template #extra>
      <ul>
        <li>
          <p>Производитель</p>
          <p>Клинцы</p>
        </li>
        <li>
          <p>Дополнительное</p>
          <p>Протевовес массой 1,5т.</p>
        </li>
        <li>
          <p>Габаритные размеры (ДxШxВ), мм</p>
          <p>g</p>
        </li>
        <li>
          <p>Грузоподъемность максимальная, т</p>
          <p>32</p>
        </li>
        <li>
          <p>Максимальный грузовой момент</p>
          <p>g</p>
        </li>
        <li>
          <p>Высота подъема максимальная, м</p>
          <p>31</p>
        </li>
        <li>
          <p>Марка шасси</p>
          <p>МАЗ</p>
        </li>
        <li>
          <p>Вылет максимальный, м</p>
          <p>g</p>
        </li>
        <li>
          <p>Вылет минимальный, м</p>
          <p></p>
        </li>
        <li>
          <p>Высота подъема при максимальном вылете, м</p>
          <p>g</p>
        </li>
        <li>
          <p>Скорость подъема/опускания груза</p>
          <p>g</p>
        </li>
        <li>
          <p>Колёсная формула</p>
          <p>6х6</p>
        </li>
        <li>
          <p>Длина стрелы, м</p>
          <p>31</p>
        </li>
        <li>
          <p>Скорость посадки</p>
          <p>g</p>
        </li>
        <li>
          <p>Частота вращения</p>
          <p></p>
        </li>
        <li>
          <p>Грузоподъёмность, кг</p>
          <p>25 000</p>
        </li>
        <li>
          <p>Максимальная глубина опускания, м</p>
          <p>g</p>
        </li>
        <li>
          <p>Вылет при максимальной грузоподъемности, м</p>
          <p>g</p>
        </li>
        <li>
          <p>Базовое шасси</p>
          <p>g</p>
        </li>
        <li>
          <p>Радиус поворота, м</p>
          <p>gg</p>
        </li>
        <li>
          <p>Полная масса автомобиля, кг</p>
          <p>gg</p>
        </li>
        <li>
          <p>ТИП ТРАНСПОРТНОГО СРЕДСТВА</p>
          <p>Автокран</p>
        </li>
      </ul>
    </template>
  </ItemComponent>
</template>

<style scoped>
ul {
  display: grid;
  grid-template-columns: 1fr;
  flex-wrap: wrap;
  gap: 12px;
  font: var(--font-caption);
}

li {
  line-height: 1.2;
}

@media (min-width: 1024px) {
  ul {
    grid-template-columns: 1fr 1fr;
  }
}
</style>
