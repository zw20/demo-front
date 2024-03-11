<script setup lang="ts">

</script>

<template>
  <div class="footer">
    <div class="box">
      <div class="num">2000 +</div>
      <div class="description">合作体育机构</div>
    </div>
    <div class="box">
      <div class="num">150 +万</div>
      <div class="description">累计运营比赛场次</div>
    </div>
    <div class="box">
      <div class="num">1.2 +万</div>
      <div class="description">年度直播场次</div>
    </div>
    <div class="box">
      <div class="num">30 +万</div>
      <div class="description">累计保险服务人次</div>
    </div>
    <div class="box">
      <div class="num">20 +万</div>
      <div class="description">月度活跃赛事参与用户</div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.footer {
  width: 1200px;
  height: 316px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  .box {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    width: 240px;
    .num {
      color: #cd322d;
      font-size: 42px;
    }
    .description {
      font-size: 18px;
      color: grey;
    }
  }
}
</style>