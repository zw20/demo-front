<script setup lang="ts">

</script>

<template>
  <div class="guys">
    <div class="info">
      <div class="title">合作伙伴们</div>
      <div class="desc">超过2000+个生态合作伙伴，提供技术、部署、服务全链路支持</div>
      <img src="../assets/guys/guys_info.png" class="img" alt="none"/>
    </div>
  </div>
</template>

<style scoped lang="scss">
.guys {
  width: 100%;
  height: 1078px;
  background-image: url('../assets/guys/guys_bg.png');
  background-size: 100% 100%;
  position: relative;
  .info {
    width: 1200px;
    position: absolute;
    top: 60px;
    left: 50%;
    transform: translate(-50%);
    margin: 0 auto;
    .title {
      font-size: 30px;
      color: #fff;
      font-weight: 500;
    }
    .desc {
      font-size: 16px;
      color: hsla(0, 0%, 100%, .6);
      margin-top: 14px;
    }
  }
  .img {
    width: 891px;
    height: 779px;
    position: absolute;
    top: 450px;
    left: 50%;
    transform: translate(-50%, -35%);
  }
}
</style>