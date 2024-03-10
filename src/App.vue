<script setup lang="ts">
import MyNav from "@/components/MyNav.vue";
import Carousel from "@/components/carousel.vue";
</script>

<template>
  <div class="app">
    <my-nav />
    <carousel />
  </div>
</template>

<style scoped>
.app {
  min-width: 100vw;
}
</style>
