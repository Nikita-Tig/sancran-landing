<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import logoLight from '@/assets/logoLight.svg'
import logoDark from '@/assets/logoDark.svg'
import ContactButton from './components/ContactButton.vue'
</script>

<template>
  <header>
    <RouterLink to="/">
      <picture>
        <source :srcset="logoDark" media="(prefers-color-scheme: dark)" />
        <source :srcset="logoLight" media="(prefers-color-scheme: light)" />
        <img :src="logoLight" alt="СанКран" class="logo" />
      </picture>
    </RouterLink>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Главная</RouterLink>
        <RouterLink to="/about">О Нас</RouterLink>
        <!-- <RouterLink to="/ab">About</RouterLink> -->
      </nav>
    </div>
    <ContactButton>Связатся</ContactButton>
  </header>
  <RouterView />
</template>

<style scoped>
header {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: var(--color-background);
  padding: 12px 24px;
}

.logo {
  display: block;
  width: 160px;
  height: 83px;
}

nav {
  display: flex;
  place-items: center;
  width: 100%;
  font-size: 16px;
  text-align: center;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
  white-space: nowrap;
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    width: 100%;
    display: flex;
    place-items: center;
  }

  nav {
    text-align: center;
    margin-left: -1rem;
    font-size: 24px;
  }
}
</style>
