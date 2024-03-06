<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import MyNav from './components/MyNav.vue'
</script>

<template>
  <div style="width: 100vw; height: 100vh; background-color: #FFFFFF;">
    <my-nav />
    <RouterView />
  </div>
</template>

<style scoped>
</style>
