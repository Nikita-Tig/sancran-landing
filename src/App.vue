<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import logoLight from '@/assets/images/logoLight.svg'
import logoDark from '@/assets/images/logoDark.svg'
import ContactButton from './components/shared/ContactButton.vue'
import ModalComponent from './components/shared/ModalComponent.vue'
import { provide, ref } from 'vue'
import IconMapPin from './assets/icons/IconMapPin.vue'

const showModal = ref(false)

function openModal() {
  showModal.value = true
}

function closeModal() {
  showModal.value = false
}

provide('openModal', openModal)
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
    <ContactButton></ContactButton>
  </header>
  <RouterView />
  <Transition>
    <ModalComponent v-if="showModal" @close="closeModal">
      <template #default>
        <h3>Свяжитесь с нами сдесь:</h3>
        <p>
          Телефон:
          <a href="tel:+79201668121" target="_blank" rel="noopener noreferrer">+7 920 166-81-21</a>
        </p>
        <p>
          Telegram:
          <a href="https://t.me/+79201668121" target="_blank" rel="noopener noreferrer">Теодор</a>
        </p>
        <p>
          Max:
          <a
            href="https://max.ru/u/f9LHodD0cOIIWgPcRzVG_asnY2Uq0An4_NUpSRNd1Dp0ALKZIaxFl7mTCtk"
            target="_blank"
            rel="noopener noreferrer"
            >Теодор</a
          >
        </p>
        <p>
          E-mail:
          <a
            href="mailto:theo2978@yandex.ru?subject=По поводу автокрана&body=Здравствуйте,%20я%20хотел%20бы%20узнать%20больше."
            target="_blank"
            rel="noopener noreferrer"
            >theo2978@yandex.ru</a
          >
        </p>
      </template>
    </ModalComponent>
  </Transition>
  <footer>
    <div class="address">
      <IconMapPin />
      <p>Нижегородская область, г. Бор</p>
    </div>
  </footer>
</template>

<style scoped>
header {
  width: 100vw;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: var(--color-background);
  padding: 4px 8px;
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1;
}

.logo {
  display: block;
  max-width: 158px;
  max-height: 83px;
}

nav {
  display: flex;
  flex-direction: column;
  place-items: center;
  width: 100%;
  font-size: var(--font-h3);
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
  border-top: 1px solid var(--color-border);
  white-space: nowrap;
}

nav a:first-of-type {
  border: 0;
}

.v-enter-active {
  transition: opacity 0.35s ease;
}
.v-leave-active {
  transition: opacity 0.1s ease;
}

.v-enter-from,
.v-leave-to {
  opacity: 0;
}

h3 {
  font: var(--font-h3);
}

footer {
  display: flex;
  background-color: var(--color-background);
  padding: 4px 8px;
}

.address {
  display: flex;
  gap: 8px;
}

@media (min-width: 1024px) {
  header {
    padding: 12px 24px;
    display: flex;
    place-items: center;
  }

  nav {
    flex-direction: row;
    text-align: center;
    margin-left: -1rem;
    font-size: 24px;
  }

  nav a {
    border-top: none;
    border-left: 1px solid var(--color-border);
  }

  footer {
    padding: 12px 24px;
  }
}
</style>
