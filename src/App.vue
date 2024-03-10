<script setup lang="ts">
import MyNav from "@/components/MyNav.vue";
import Carousel from "@/components/carousel.vue";
</script>

<template>
  <div class="app">
    <my-nav />
    <div style="height: 80px;"></div>
    <carousel />
  </div>
</template>

<style scoped>
.app {
  min-width: 100vw;
}
</style>
