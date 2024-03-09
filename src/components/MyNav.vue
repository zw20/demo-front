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

const match = ref(['赛事报名', '赛事检录', '积分排名', '数据统计', '赛事公告', '赛事视频', '停赛通知', '嵌入公众号'])
const club = ref(['活动报名', '人员管理', '队费缴纳', '战术安排', '数据统计', '相册&视频', 'VIP俱乐部'])
const live = ref(['高清视频', '多机位直播', '标准直播', '赛事宣传片', '俱乐部Vlog'])
const insure = ref(['运动意外伤害险', '场馆责任险', '赛事责任险', '教练责任险'])
const teach = ref(['校区&师资&学员管理', '营销获客', '即将发布', '缴费收款', '点名考勤', '排课通知', '家校互动'])
const venue = ref(['预定排场', '缴费收款', '长包设置', '临时锁场', '嵌入微信', '会员管理', '财务分析'])
const org = ref(['会员管理', '缴费收款', '考核培训', '赛事运营', '品牌展示'])

const product = ref()
const programmatic = ref()
function showProduct() {
  activeIndex.value = 0
  product.value.style.display = 'block'
}
function closeProduct() {
  activeIndex.value = -1
  product.value.style.display = 'none'
}
function showProgrammatic() {
  activeIndex.value = 1
  programmatic.value.style.display = 'block'
}
function closeProgrammatic() {
  activeIndex.value = 1
  programmatic.value.style.display = 'none'
}
</script>

<template>
  <div class="my-nav">
    <div class="nav">
      <div class="left">
        <img class="logo" src="../assets/my_nav/logo.png" alt="Logo">
        <img class="qw" src="../assets/my_nav/qw.png" alt="QW">
        <div class="tabs">
          <div class="tab" :class="activeIndex === 0 ? 'action' : ''" @mouseenter="showProduct" @mouseleave="closeProduct">产品系列</div>
          <div class="bor mar-left"></div>
          <div class="tab mar-left" :class="activeIndex === 1 ? 'action' : ''" @mouseenter="showProgrammatic" @mouseleave="closeProgrammatic">解决方案</div>
          <div class="bor mar-left"></div>
          <div class="tab mar-left" style="cursor: pointer" :class="activeIndex === 2 ? 'action' : ''">客户案例</div>
        </div>
      </div>
      <button class="btn">联系我们</button>
    </div>
    <div class="product" ref="product">
      <div class="popup-box" @mouseenter="showProduct" @mouseleave="closeProduct">
        <div class="item-box box1">
          <div class="item">
            <a href="javascript:" class="title">办赛组织</a>
            <div class="other-box"></div>
            <div class="info" v-for="item in match">
              <div class="name">{{ item }}</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">俱乐部管理</a>
            <div class="other-box"></div>
            <div class="info" v-for="item in club">
              <div class="name">{{ item }}</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">直播集锦</a>
            <div class="other-box"></div>
            <div class="info" v-for="item in live">
              <div class="name">{{ item }}</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">保险保障</a>
            <div class="other-box"></div>
            <div class="info" v-for="item in insure">
              <div class="name">{{ item }}</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">体培招生</a>
            <div class="other-box"></div>
            <div class="info" v-for="item in teach">
              <div class="name">{{ item }}</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">订场缴费</a>
            <div class="other-box"></div>
            <div class="info" v-for="item in venue">
              <div class="name">{{ item }}</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">协会运营</a>
            <div class="other-box"></div>
            <div class="info" v-for="item in org">
              <div class="name">{{ item }}</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="programmatic" ref="programmatic">
      <div class="popup-box" @mouseenter="showProgrammatic" @mouseleave="closeProgrammatic">
        <div class="item-box box2">
          <div class="item">
            <a href="javascript:" class="title">赛事运营</a>
            <div class="other-box"></div>
            <img class="img" src="../assets/my_nav/match.png" alt="">
            <div class="description">
              <div class="min-title">赛事通</div>
              <div class="detail">提供赛事运营全站一体化解决方案</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">体育培训</a>
            <div class="other-box"></div>
            <img class="img" src="../assets/my_nav/match.png" alt="">
            <div class="description">
              <div class="min-title">邦教练</div>
              <div class="detail">招生排课好方便 青训就用邦教练</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">场馆运营</a>
            <div class="other-box"></div>
            <img class="img" src="../assets/my_nav/match.png" alt="">
            <div class="description">
              <div class="min-title">智慧场馆</div>
              <div class="detail">搭建私域 球队维护 赛事安排 场馆直播</div>
            </div>
          </div>
          <div class="item">
            <a href="javascript:" class="title">协会管理</a>
            <div class="other-box"></div>
            <img class="img" src="../assets/my_nav/match.png" alt="">
            <div class="description">
              <div class="min-title">体协+</div>
              <div class="detail">会员注册 会费管理 裁判管理 检录核销</div>
            </div>
          </div>
        </div>
      </div>
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
          height: 80px;
          display: flex;
          align-items: center;
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
      cursor: pointer;
    }
  }
  .popup-box {
    width: 100%;
    min-height: 260px;
    background-color: #fff;
    cursor: pointer;
    display: flex;
    justify-content: center;
    .box1 {
      padding: 32px 36px;
    }
    .box2 {
      padding: 30px 242px;
    }
    .item-box {
      min-width: 1220px;
      box-sizing: border-box;
      display: flex;
      justify-content: flex-start;
      .item {
        width: 150px;
        margin-right: 15px;
        .title {
          display: block;
          height: 40px;
          color: #333333;
          text-decoration: none;
        }
        .other-box {
          border-top: 1px #EBEEF5 solid;
          width: 100px;
          height: 20px;
        }
        .info {
          height: 17px;
          color: #666;
          font-size: 12px;
          margin-bottom: 10px;
          .name {
            font-size: 12px;
          }
        }
        .img {
          width: 65px;
          height: 80px;
        }
        .description {
          width: 100px;
          .min-title {
            font-size: 14px;
            color: #191919;
          }
          .detail {
           font-size: 12px;
          }
        }
      }
    }
  }
  .product {
    width: 100%;
    display: none;
    position: absolute;
    top: 80px;
    z-index: 1;
  }
  .programmatic {
    width: 100%;
    display: none;
    position: absolute;
    top: 80px;
    z-index: 1;
  }
}
</style>