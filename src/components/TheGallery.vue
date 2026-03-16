<script setup lang="ts">
import { computed, onMounted, ref } from 'vue'
import CardComponent from './shared/CardComponent.vue'
import machinery0 from '../assets/images/gallery/machinery0.png'
import machinery1 from '../assets/images/gallery/machinery1.png'
import machinery2 from '../assets/images/gallery/machinery2.png'
import machinery3 from '../assets/images/gallery/machinery3.png'

type photo = {
  img: string
  id: number
}

const photos: photo[] = [
  {
    img: machinery0,
    id: 0,
  },
  {
    img: machinery1,
    id: 1,
  },
  {
    img: machinery2,
    id: 2,
  },
  {
    img: machinery3,
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
  return photos.slice(index.value, index.value + count)
})

function next() {
  if (index.value + count < photos.length) {
    index.value++
  } else {
    index.value = 0
  }
}

function prev() {
  if (index.value > 0) {
    index.value--
  } else {
    index.value = photos.length - count
  }
}
</script>

<template>
  <div class="gallery">
    <h3>Галерея наших работ</h3>
    <div class="cards">
      <CardComponent v-for="card in cardsToShow" v-bind:key="card.id">
        <template #img><img :src="card.img" /></template>
      </CardComponent>
    </div>
    <div class="buttons">
      <button @click="prev">←</button>
      <button @click="next">→</button>
    </div>
  </div>
</template>

<style scoped>
.gallery {
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
  .gallery {
    max-width: 1200px;
  }

  .cards {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 16px;
  }
}
</style>
