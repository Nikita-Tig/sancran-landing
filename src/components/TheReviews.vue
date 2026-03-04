<script setup lang="ts">
import { computed, onMounted, ref } from 'vue'
import CardComponent from './shared/CardComponent.vue'

type review = {
  img: string
  heading: string
  content: string
  id: number
}

const reviews: review[] = [
  {
    img: 'src/assets/images/craneHangar.png',
    heading: 'Профессионалы',
    content: 'Выполнили непростую работу на высшем уровне',
    id: 0,
  },
  {
    img: 'src/assets/images/craneHouse.png',
    heading: 'Пунктуальность',
    content: 'Приехали вовремя и быстро были готовы выполнять работу',
    id: 1,
  },
  {
    img: 'src/assets/images/craneWoodHouse.png',
    heading: 'Доступность',
    content: 'Готовы приехать в любое назначенное время',
    id: 2,
  },
  {
    img: 'src/assets/images/craneWoodWork.png',
    heading: 'Цена-качество',
    content: 'Цены соответствуют качеству услуг',
    id: 3,
  },
]

const index = ref(0)
const isMobile = ref(false)
let count = 3

function updateMedia() {
  isMobile.value = window.matchMedia('(max-width: 1024px)').matches
}

onMounted(() => {
  updateMedia()
  window.addEventListener('resize', updateMedia)
})

const cardsToShow = computed(() => {
  count = isMobile.value ? 1 : 3
  return reviews.slice(index.value, index.value + count)
})

function next() {
  if (index.value + count < reviews.length) {
    index.value++
  } else {
    index.value = 0
  }
}

function prev() {
  if (index.value > 0) {
    index.value--
  } else {
    index.value = reviews.length - count
  }
}
</script>

<template>
  <div class="reviews">
    <h3>Что о нас говорят</h3>
    <div class="cards">
      <CardComponent v-for="card in cardsToShow" v-bind:key="card.id">
        <template #img><img :src="card.img" /></template>
        <template #heading>{{ card.heading }}</template>
        <template #default>{{ card.content }}</template>
      </CardComponent>
    </div>
    <div class="buttons">
      <button @click="prev">←</button>
      <button @click="next">→</button>
    </div>
  </div>
</template>

<style scoped>
.reviews {
  display: flex;
  flex-direction: column;
  gap: 20px;
  background-color: var(--color-background-soft);
  padding: 24px;
  width: 100%;
}

h3 {
  font: var(--font-h3);
}

.cards {
  display: flex;
  justify-content: center;
}

img {
  max-width: 100%;
  display: inline-block;
}

.buttons {
  align-self: center;
  display: flex;
  gap: 42px;
}

button {
  padding: 10px 20px;
  font: var(--font-h3);
}

@media (min-width: 1024px) {
  .reviews {
    max-width: 1200px;
  }

  .cards {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 16px;
  }
}
</style>
