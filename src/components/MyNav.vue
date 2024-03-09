<script setup lang="ts">
import {onMounted, ref} from 'vue'
let activeIndex = ref(-1)
onMounted(() => {
  const tabs = document.querySelectorAll('.tab')
  tabs.forEach((tab, index) => {
    tab.addEventListener('mouseenter', () => {
      activeIndex.value = index
    })
  })
  tabs.forEach(tab => {
    tab.addEventListener('mouseleave', () => {
      activeIndex.value = -1
    })
  })
})
</script>

<template>
  <div class="my-nav">
    <div class="nav">
      <div class="left">
        <img class="logo" src="../assets/my_nav/logo.png" alt="Logo">
        <img class="qw" src="../assets/my_nav/qw.png" alt="QW">
        <div class="tabs">
          <div class="tab" :class="activeIndex === 0 ? 'action' : ''">产品系列</div>
          <div class="bor mar-left"></div>
          <div class="tab mar-left" :class="activeIndex === 1 ? 'action' : ''">解决方案</div>
          <div class="bor mar-left"></div>
          <div class="tab mar-left" style="cursor: pointer" :class="activeIndex === 2 ? 'action' : ''">客户案例</div>
        </div>
      </div>
      <button class="btn">联系我们</button>
    </div>
    <div class="product">
    </div>
  </div>
</template>

<style lang="scss" scoped>
.my-nav {
  min-width: 100vw;
  display: flex;
  justify-content: center;
  background-color: #FFFFFF;
  position: fixed;
  top: 0;
  z-index: 1;
  .nav {
    min-width: 1220px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 10px;
    height: 80px;
    box-sizing: border-box;
    .left {
      display: flex;
      align-items: center;
      .logo {
        width: 87px;
        height: 36px;
      }
      .qw {
        margin-left: 20px;
        width: 124px;
        height: 24px;
      }
      .tabs {
        margin-left: 80px;
        display: flex;
        align-items: center;
        .tab {
          position: relative;
          font-size: 14px;
          color: #666666;
        }
        .action {
          font-weight: 700;
          color: #409EFF;
        }
        .bor {
          width: 2px;
          height: 20px;
          background-color: #666666;
        }
        .mar-left {
          margin-left: 30px;
        }
      }
    }
    .btn {
      padding: 6px 16px;
      display: inline-block;
      font-size: 14px;
      color: #fff;
      background: #191919;
      border-radius: 2px;
      border: 1px solid #000;
    }
  }
}
</style>