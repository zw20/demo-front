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
const bgImage = ref([
  { image: new URL('@/assets/carousel/match-bg.png', import.meta.url).href, title: '赛事通', detail: '提供赛事运营全站一体化解决方案'},
  { image: new URL('@/assets/carousel/teach-bg.png', import.meta.url).href, title: '邦教练', detail: '招生排课好方便 青训就用邦教练'},
  { image: new URL('@/assets/carousel/venue-bg.png', import.meta.url).href, title: '智慧场馆', detail: '搭建私域 球队维护 赛事安排 场馆直播'},
  { image: new URL('@/assets/carousel/org-bg.png', import.meta.url).href, title: '体协+', detail: '会员注册 会费管理 裁判管理 检录核销'}
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
    <div class="info">
      <div v-for="item in bgImage" :key="item.image" class="img" :style="{ backgroundImage: `url('${item.image}')`, backgroundSize: '100% 100%'}">
        <div class="title">{{ item.title }}</div>
        <div class="detail">{{ item.detail }}</div>
        <el-button class="btn" style="width: 71px; height: 30px;" size="small">了解详情</el-button>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.carousel {
  min-width: 1220px;
  position: relative;
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
  .info {
    position: absolute;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    bottom: -155px;
    .img {
      width: 300px;
      height: 210px;
      padding: 30px 10px;
      .title {
        font-size: 20px;
        color: #FFFFFF;
      }
      .detail {
        font-size: 14px;
        color: #FFFFFF;
        margin-top: 12px;
      }
      .btn {
        margin-top: 45px;
      }
    }
  }
}
</style>