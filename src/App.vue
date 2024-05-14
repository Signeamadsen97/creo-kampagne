<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Navigation from './components/Navigation.vue';
import FooterCreo from './components/FooterCreo.vue';
</script>

<template>
  <header>
    <Navigation />
  </header>

  <RouterView />

  <footer>
    <FooterCreo/>
  </footer>
</template>

<style scoped>

</style>
