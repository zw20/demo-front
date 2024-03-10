<script setup lang="ts">
import {ref} from "vue";

const images = ref([
  {
    value1: new URL('@/assets/carousel/1-1.png', import.meta.url).href,
    value2: new URL('@/assets/carousel/1-2.png', import.meta.url).href
  },
  {
    value1: new URL('@/assets/carousel/2-1.png', import.meta.url).href,
    value2: new URL('@/assets/carousel/2-2.png', import.meta.url).href
  },
  {
    value1: new URL('@/assets/carousel/3-1.png', import.meta.url).href,
    value2: new URL('@/assets/carousel/3-2.png', import.meta.url).href
  },
  {
    value1: new URL('@/assets/carousel/4-1.png', import.meta.url).href,
    value2: new URL('@/assets/carousel/4-2.png', import.meta.url).href
  },
  {
    value1: new URL('@/assets/carousel/5-1.png', import.meta.url).href,
    value2: new URL('@/assets/carousel/5-2.png', import.meta.url).href
  }
])
</script>

<template>
  <div class="carousel">
    <el-carousel height="444px">
      <el-carousel-item v-for="item in images" :key="item.value1">
        <div class="img-box">
          <el-image class="img" style="z-index: 1" :src="item.value1" fit="fill" />
          <el-image class="img" style="z-index: 2" :src="item.value2" fit="contain" />
        </div>
      </el-carousel-item>
    </el-carousel>
  </div>
</template>

<style lang="scss" scoped>
.carousel {
  min-width: 1220px;
  padding-top: 80px;
  .img-box {
    min-width: 100%;
    height: 444px;
    position: relative;
    .img {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 444px;
    }
  }
}

</style>