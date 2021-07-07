<style>
.m64 {
  padding: 20px 40px;
}
.ugc {
  width: 100%;
  padding-bottom: 36px;
  border-radius: 40px;
  border: 1px solid #dddddd;
  box-sizing: border-box;
  display: block;
  margin-top: 20px;
}
.ugc:first-child {
  margin-top: 0px;
}
.ugc__pic {
  width: 100%;
  height: 0px;
  border-radius: 40px 40px 0px 0px;
  position: relative;
  background: no-repeat center/contain;
}
.multilook__icon {
  position: absolute;
  width: 80px;
  height: 80px;
  right: 30px;
  top: 30px;
  background: url('https://pic.bbtkids.cn/FuXAs3_GCFyN16h8HLTITN4L73NV') no-repeat center/cover;
}
.videolook__icon {
  position: absolute;
  width: 160px;
  height: 160px;
  left: 50%;
  margin-left: -80px;
  top: 50%;
  margin-top: -80px;
  background: url('https://pic.bbtkids.cn/FuUdMfegLLmTpQ_IaFHN86YSiToL') no-repeat center/cover;
}
.m64__user__box {
  width: 100%;
  height: 112px;
  display: flex;
  align-items: center;
  padding: 0px 28px;
}
.m64__user__icon {
  width: 60px;
  height: 60px;
  border-radius: 50%;
  margin-right: 18px;
  background: #fff no-repeat center/contain;
}
.m64__user__name {
  font-size: 24px;
  font-family: PingFangSC-Medium;
  font-weight: 500;
  color: #000000;
}
.m64__desc__detail {
  font-size: 22px;
  font-family: PingFangSC-Regular;
  font-weight: 400;
  color: #aaaaaa;
  margin-right: 10px;
}
.m64__ugc__desc {
  padding: 0px 28px;
  font-size: 28px;
  font-family: PingFangSC-Regular;
  font-weight: 400;
  color: #111111;
  margin-top: 6px;
}
</style>

<template>
  <div class="m64">
    <navigator class="ugc bgc-wt" v-for="(ugc, index) in tplData.ugcInfoList" :key="index" :url="ugc.jumpUrl">
      <div class="ugc__pic" :style="{ backgroundImage: 'url(' + ugc.pic.picUrl + ')', paddingTop: ugc.ratio }">
        <div class="multilook__icon" v-if="ugc.type === 1"></div>
        <div class="videolook__icon" v-if="ugc.type === 2"></div>
      </div>
      <div class="m64__user__box">
        <div class="m64__user__icon" :style="{ backgroundImage: 'url(' + ugc.sender.faceUrl + ')' }"></div>
        <div class="m64__user__desc">
          <p class="m64__user__name">{{ ugc.sender.nick }}</p>
          <p class="m64__desc__detail line line-1" v-if="ugc.sender.goodAtList.length > 0">
            擅长种草<template v-for="good in ugc.sender.goodAtList">{{ good }}</template>
          </p>
        </div>
      </div>
      <p class="m64__ugc__desc line line-4">{{ ugc.desc }}</p>
    </navigator>
  </div>
</template>

<script>
export default {
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  computed: {},
  data() {
    return {}
  },
  mounted() {
    this.tplData.ugcInfoList.map((ugc, index) => {
      let ratio = parseFloat(1 / ugc.pic.w2hRatio)
      ratio = ratio >= 0.5 && ratio <= 1.86 ? ratio : ratio > 1.86 ? 1.86 : 0.5
      ratio = ratio * 100 + '%'
      this.$set(this.tplData.ugcInfoList[index], 'ratio', ratio)
    })
    // console.log(this.tplData.ugcInfoList)
  }
}
</script>
