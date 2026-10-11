<script setup>
import AppHeader from './components/AppHeader.vue'
import HeroSection from './components/HeroSection.vue'
import AppFooter from './components/AppFooter.vue'
</script>

<template>
  <div class="app-layout">
    <AppHeader />
    <HeroSection />
    <AppFooter />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  margin: 0;
  padding: 0;
  background-color: #f8fafc;
  font-family: 'Plus Jakarta Sans', system-ui, -apple-system, sans-serif;
  overflow-x: hidden;
}

.app-layout {
  min-height: 100vh;
  width: 100%;
}
</style>
