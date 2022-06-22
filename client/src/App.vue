<script setup lang="ts">
import { RouterView } from 'vue-router'
import Footer from '@/components/Footer.vue'
import Header from '@/components/Header.vue'
</script>

<template>
  <div class="app">
    <header>
      <Header />
    </header>
    <div>
      <RouterView />
    </div>
    <div class="filler"></div>
    <footer>
      <Footer />
    </footer>
  </div>
</template>

<style scoped>
.app {
  height: 100vh;
  display: grid;
  grid-template-rows: auto auto 1fr auto;
  grid-template-columns: minmax(0, auto);
}
</style>
