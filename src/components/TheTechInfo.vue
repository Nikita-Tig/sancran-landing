<script setup lang="ts">
import ItemComponent from './shared/ItemComponent.vue'
</script>

<template>
  <ItemComponent class="center">
    <template #subHeading>Техничкеские характеристики КС-55713-6К-4 автокран 25 т.</template>
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
          <p>12000х2550х4000</p>
        </li>
        <li>
          <p>Грузоподъемность максимальная, т</p>
          <p>25</p>
        </li>
        <li>
          <p>Максимальный грузовой момент кНм</p>
          <p>85</p>
        </li>
        <li>
          <p>Высота подъема максимальная, м</p>
          <p>31,8</p>
        </li>
        <li>
          <p>Марка шасси</p>
          <p>МАЗ</p>
        </li>
        <li>
          <p>Вылет максимальный, м</p>
          <p>8,0</p>
        </li>
        <li>
          <p>Вылет минимальный, м</p>
          <p>2,5</p>
        </li>
        <li>
          <p>Высота подъема при максимальном вылете, м</p>
          <p>4,5</p>
        </li>
        <li>
          <p>Скорость подъема/опускания груза, м/с</p>
          <p>0,20-0,40</p>
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
          <p>Скорость посадки м/с</p>
          <p>0,007</p>
        </li>
        <li>
          <p>Частота вращения (Номинальная) об/мин</p>
          <p>0,96</p>
        </li>
        <li>
          <p>Грузоподъёмность, кг</p>
          <p>25 000</p>
        </li>
        <li>
          <p>Максимальная глубина опускания, м</p>
          <p>10</p>
        </li>
        <li>
          <p>Вылет при максимальной грузоподъемности, м</p>
          <p>3,4</p>
        </li>
        <li>
          <p>Базовое шасси</p>
          <p>МАЗ-6302С5</p>
        </li>
        <li>
          <p>Радиус поворота, м</p>
          <p>13,2</p>
        </li>
        <li>
          <p>Полная масса автомобиля, кг</p>
          <p>22 820</p>
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
