<script setup lang="ts">
import {ref} from "vue";

let a = [
  { value: '1', label: '首页' },
  { value: '2', label: '产品' },
  { value: '3', label: '案例' },
  { value: '4', label: '关于我们' },
  { value: '5', label: '加入我们' }
]
let active = ref('4')
function changeActive(value) {
  active.value = value
}
function hoverTab(index) {
  if (a[index].value === active.value) return
  const tabs = document.querySelectorAll('.tab')
  const tab = tabs[index]
  tab.style.width = a[index].label.length * 13 + 'px'
}
function leaveTab(index) {
  if (a[index].value === active.value) return
  const tabs = document.querySelectorAll('.tab')
  const tab = tabs[index]
  tab.style.width = '0px'
}
</script>

<template>
  <div class="my-nav">
    <img class="img" src="../assets/homePage/logo.png" alt="logo">
    <ul class="u">
      <li class="l" v-for="(item, index) in a" @click="changeActive(item.value)" @mouseenter="hoverTab(index)" @mouseleave="leaveTab(index)">
        <span>{{ item.label }}</span>
        <div class="tab" style="transition: width 0.3s" :style="item.value === active ? { width:  item.label.length * 13 + 'px', left: item.label.length + 'px' } : { left: item.label.length + 'px' }"></div>
      </li>
    </ul>
  </div>
</template>

<style lang="scss">
.my-nav {
  height: 60px;
  background-color: #ffffff;
  color: #333333;
  display: flex;
  padding: 0 20px;
  justify-content: space-between;
  align-items: center;
  .img {
    width: 90px;
    height: 30px;
  }
  .u {
    display: flex;
    .l {
      list-style: none;
      margin-right: 10px;
      position: relative;
      cursor: pointer;
      .tab {
        height: 2px;
        background: -webkit-linear-gradient(left, #1ebbf0 30%, #39dfaa);
        position: absolute;
        top: 23px;
        margin: 0 auto;
        transition: width;
        transition-duration: 0.3s;
      }
    }
  }
}
</style>
