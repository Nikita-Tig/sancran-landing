<script setup lang="ts">
import TheAbout from '@/components/TheAbout.vue'
import TheGallery from '@/components/TheGallery.vue'
import TheReviews from '@/components/TheReviews.vue'
</script>

<template>
  <main>
    <TheAbout />
    <TheReviews />
    <TheGallery />
  </main>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
