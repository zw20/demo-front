<script setup lang="ts">
import { ref } from "vue";

const actionInfo = ref([
  { image: new URL('@/assets/action/01.png', import.meta.url).href, title: '办赛组织', info: ['赛事运营管理数据化。', '针对杯赛、联赛等多种赛制，实现专业的信息化招募，管理，执行，运营、传播和营销。', '支持足球、篮球、棒球、排球、乒乓球、羽球、等9大类型。'] },
  { image: new URL('@/assets/action/02.png', import.meta.url).href, title: '俱乐部管理', info: ['在线管理运营俱乐部，让每个Club都变成聚乐部', '通过活动报名，出勤统计，数据统计，球队相册等插件。记录大家每一次活动的精彩瞬间。'] },
  { image: new URL('@/assets/action/03.png', import.meta.url).href, title: '直播集锦', info: ['LiveCut直播黑科技·赛后一秒成集锦', '基于智能手机的体育比赛多人直播系统。边直播，边打点，精彩瞬间一个也不放过。'] },
  { image: new URL('@/assets/action/04.png', import.meta.url).href, title: '保险保障', info: ['保监会备案的专业运动险，大平台有保障。', '适合团队运动各种场景，报案快，出险快，赔偿快'] },
  { image: new URL('@/assets/action/05.png', import.meta.url).href, title: '体培招生', info: ['围绕中小型体育培训机构师资管理、营销获客、排课通知、点名考勤、家校互动、缴费收款六大模块', '讲运动的培训和运动赛事直播结合的新SaaS系统'] },
  { image: new URL('@/assets/action/06.png', import.meta.url).href, title: '订场缴费', info: ['为中小型场馆运营者，打造极简运营工具。', '通过预定、锁场、长包、约战、会员多维度工具', '实现无纸化办公和运营'] },
  { image: new URL('@/assets/action/07.png', import.meta.url).href, title: '协会运营', info: ['赋能协会，给与一些列工具快速建立协会框架，搭建协会信息资产、数据资产和赛事资产', '让协会运营成为动动手机就能轻易完成的工作'] }
])
let actionIndex = ref(0)
function doing(index) {
  actionIndex.value = index
}

const box_1 = ref([
  { icon: '', title: '赛事报名', info: '自定义报名信息，支持微信群共享'},
  { icon: '', title: '赛事检录', info: '检录信息化，在线检录，支持下载打印'},
  { icon: '', title: '积分排行', info: '自动计算积分，榜单,支持海报分享'},
  { icon: '', title: '数据统计', info: '支持各种赛事规则，灵活，弹性'},
  { icon: '', title: '赛事公告', info: '赛事通知推送，方便办赛组织'},
  { icon: '', title: '赛事视频', info: '直播剪辑黑科技，赛后一秒变集锦'},
  { icon: '', title: '停赛通知', info: '自动规则计算，降低办赛成本'},
  { icon: '', title: '嵌入公众号', info: '打造属于赛事自己的主页'}
])

const box_2 = ref([
  { icon: '', title: '活动报名', info: '微信平台最受欢迎团队运动日程管理小程序'},
  { icon: '', title: '人员管理', info: '球员、教练、粉丝统一管理'},
  { icon: '', title: '队费缴纳', info: '俱乐部小账本会员费 单次费 季度费都支持'},
  { icon: '', title: '战术安排', info: '基于H5的动画战术板明天比赛怎么提，球队线上聊'},
  { icon: '', title: '数据统计', info: '出勤、进球、助攻... ...支持多种榜单，球队大腿轻松浮现'},
  { icon: '', title: '相册&视频', info: '球队私有空间，精彩瞬间永不删除'},
  { icon: '', title: 'VIP俱乐部', info: '打造俱乐部专业范儿装备DIY｜球队Vlog｜球队活动策划'}
])

const box_3 = ref([
  { icon: '', title: '高清直播', info: '高清摄像机服务'},
  { icon: '', title: '多机位直播', info: '支持多角度多机位，多流直播'},
  { icon: '', title: '标准直播', info: '智能手机轻便直播'},
  { icon: '', title: '赛事宣传片 [服务]', info: '赛前宣传，赛后传播你怎么可能少了一个酷炫的宣传片'},
  { icon: '', title: '俱乐部Vlog [服务]', info: '每个进球，每次呐喊，每滴流汗每一帧汇聚着我们拼搏的故事'}
])

const box_4 = ref([
  { icon: '', title: '球类运动意外保障', info: '天计划、月计划、年计划总有一款适合你'},
  { icon: '', title: '场馆责任险', info: '场馆运营定制险种疫情复工保障'},
  { icon: '', title: '赛事责任险', info: '赛事运营定制险种疫情复工保障'},
  { icon: '', title: '教练责任险', info: '体培运营定制险种疫情复工保障'}
])

const box_5 = ref([
  { icon: '', title: '球类运动意外保障', info: '天计划、月计划、年计划总有一款适合你'},
  { icon: '', title: '场馆责任险', info: '场馆运营定制险种疫情复工保障'},
  { icon: '', title: '赛事责任险', info: '赛事运营定制险种疫情复工保障'},
  { icon: '', title: '教练责任险', info: '体培运营定制险种疫情复工保障'}
])
</script>

<template>
  <div class="actions">
    <div class="action" v-for="(item, index) in actionInfo" :class="index === actionIndex ? 'border' : ''" :key="item.image" @click="doing(index)">
      <el-image :src="item.image" style="width: 56px; height: 60px;"></el-image>
      <div style="color: #000000; font-size: 18px; margin-top: 5px">{{ item.title }}</div>
    </div>
  </div>
  <div class="detail">
    <div class="action_title">
      <div class="title">{{ actionInfo[actionIndex].title }}</div>
      <div class="info">
        <p v-for="item in actionInfo[actionIndex].info" style="padding-bottom: 12px">{{ item }}</p>
      </div>
      <el-button style="background-color: #000000; border-radius: 2px; width: 117px; height: 36px;">
        <span style="color: #FFFFFF">了解产品</span>
      </el-button>
    </div>
    <div class="boxes" v-if="actionIndex === 0">
      <div class="box" v-for="item in box_1">
        <div class="box-title"><img src="../assets/action/icon.png" style="width: 20px; height: 20px; margin-right: 10px" alt="icon">{{ item.title }}</div>
        <div class="box-info">{{ item.info }}</div>
      </div>
      <div style="width: 280px;"></div>
    </div>
    <div class="boxes" v-else-if="actionIndex === 1">
      <div class="box" v-for="item in box_2">
        <div class="box-title"><img src="../assets/action/icon.png" style="width: 20px; height: 20px; margin-right: 10px" alt="icon">{{ item.title }}</div>
        <div class="box-info">{{ item.info }}</div>
      </div>
      <div style="width: 280px;"></div>
    </div>
    <div class="boxes" v-else-if="actionIndex === 2">
      <div class="box" v-for="item in box_3">
        <div class="box-title"><img src="../assets/action/icon.png" style="width: 20px; height: 20px; margin-right: 10px" alt="icon">{{ item.title }}</div>
        <div class="box-info">{{ item.info }}</div>
      </div>
      <div style="width: 280px;"></div>
    </div>
    <div class="boxes" v-else-if="actionIndex === 3">
      <div class="box" v-for="item in box_4">
        <div class="box-title"><img src="../assets/action/icon.png" style="width: 20px; height: 20px; margin-right: 10px" alt="icon">{{ item.title }}</div>
        <div class="box-info">{{ item.info }}</div>
      </div>
      <div style="width: 280px;"></div>
    </div>
    <div class="boxes" v-else>
      <div class="box" v-for="item in box_5">
        <div class="box-title"><img src="../assets/action/icon.png" style="width: 20px; height: 20px; margin-right: 10px" alt="icon">{{ item.title }}</div>
        <div class="box-info">{{ item.info }}</div>
      </div>
      <div style="width: 280px;"></div>
    </div>
  </div>
</template>
<div style="height: 350px; background-color:#FFFFFF;"></div>
<style scoped lang="scss">
.actions {
  padding-top: 186px;
  background-color: #FFFFFF;
  display: flex;
  justify-content: center;
  .action {
    width: 168px;
    height: 105px;
    //border-radius: 5px;
    display: flex;
    flex-flow: column;
    align-items: center;
    cursor: pointer;
  }
  .border {
    border-bottom: 3px #cc4440 solid;
  }
}
.detail {
  margin: 0 auto;
  width: 1200px;
  min-height: 496px;
  max-height: 540px;
  display: flex;
  padding-top: 86px;
  .action_title {
    width: 240px;
    .title {
      font-size: 24px;
      color: #191919;
    }
    .info {
      padding-top: 31px;
      height: 245px;
      font-size: 14px;
      color: #616262;
    }
  }
  .boxes {
    width: 960px;
    padding-left: 64px;
    box-sizing: border-box;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    align-content: flex-start;
    .box {
      width: 280px;
      min-height: 110px;
      background-color: #fff;
      border-radius: 6px;
      padding: 17px 13px;
      box-sizing: border-box;
      margin-bottom: 20px;
      .box-title {
        color: #191919;
        font-size: 16px;
        font-weight: 500;
        display: flex;
        align-items: center;
      }
      .box-info {
        color: #666;
        font-size: 14px;
        margin-top: 8px;
        margin-left: 30px;
        line-height: 24px;
      }
    }
  }
}
</style>