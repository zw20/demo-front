<script setup lang="ts">
import MyNav from "@/components/MyNav.vue";
import Carousel from "@/components/Carousel.vue";
import Actions from "@/components/Actions.vue"
import MyFooter from "@/components/MyFooter.vue";
import Guys from "@/components/Guys.vue";
</script>

<template>
  <div class="app">
    <my-nav />
    <div style="height: 80px;"></div>
    <carousel />
    <actions />
    <my-footer />
    <guys />
  </div>
</template>

<style scoped>
.app {
  min-width: 100vw;
}
</style>
