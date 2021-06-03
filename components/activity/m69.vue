<style scoped>
.page {
  padding: 44px 30px 130px;
  background: url('https://pic.bbtkids.cn/FmMNGrZ6wP18AKxqvld2aWdiXiGj') no-repeat top center/100% auto;
}

.section {
  display: block;
  margin-bottom: 30px;
  border-radius: 54px;
  background: #fff;
  box-shadow: 0 0 30px 0 rgba(0, 0, 0, 0.09);
  overflow: hidden;
}

/* 拼团部分 */
.unit-section {
  padding: 0 30px 30px;
}

.unit-item {
  position: relative;
  display: flex;
  align-items: center;
  padding: 20px 0;
  border-bottom: 1px solid #eee;
}

.unit-badge {
  position: absolute;
  right: -30px;
  bottom: 0;
  width: 164px;
  height: 168px;
  background: no-repeat center/contain;
}

.uitem__image {
  position: relative;
  display: block;
  width: 200px;
  height: 200px;
  border-radius: 38px;
  overflow: hidden;
  background: no-repeat center/contain;
}

.uitem__image:before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  border-radius: 38px;
  background: rgba(0, 0, 0, 0.02);
}

.uitem__main {
  flex: 1;
  margin-left: 20px;
}

.uitem__name {
  height: 88px;
  color: #555;
  line-height: 44px;
}

.uitem__name:before {
  content: '阶梯团';
  display: inline-block;
  vertical-align: middle;
  margin-right: 16px;
  padding: 0 10px;
  height: 32px;
  color: #c68f61;
  font-size: 18px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
  line-height: 28px;
  text-align: center;
  border: 2px solid #c68f61;
  border-radius: 10px;
  background: #fff9f3;
  box-sizing: border-box;
}

.uitem__name__txt {
  display: inline-block;
  vertical-align: middle;
}

.uitem__status {
  margin: 20px 0;
  height: 34px;
  font-size: 0;
}

.cd,
.cd__subfix {
  display: inline-block;
  vertical-align: middle;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
}

.cd {
  margin-right: 20px;
  padding: 0 4px;
  min-width: 32px;
  height: 32px;
  color: #fff;
  font-size: 20px;
  text-align: center;
  line-height: 32px;
  border-radius: 6px;
  box-sizing: border-box;
  background: #454144;
  position: relative;
}
.cd:nth-child(3) {
  margin-right: 5px;
}
.cd:nth-child(1):after,
.cd:nth-child(2):after {
  content: ':';
  display: inline-block;
  color: #454144;
  left: 40px;
  position: absolute;
}
.cd__subfix {
  color: #454144;
  font-size: 24px;
}

.finish__time {
  padding-top: 2px;
  color: #aaa;
  font-size: 20px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  line-height: 32px;
}

.uitem__price {
  font-size: 34px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}

.uitem__price:before {
  content: '最低到手价:';
  display: inline-block;
  color: #000;
  font-size: 20px;
  font-family: PingFangSC-Regular, PingFangTC-Regular, PingFangHK-Regular, sans-serif;
  font-weight: normal;
}

.unit-progress__wrapper {
  margin: 50px 0 40px;
  position: relative;
}

.unit-progress__wrapper:before {
  content: '';
  position: absolute;
  top: -17px;
  left: 50%;
  width: 48px;
  height: 48px;
  border-radius: 10px;
  transform-origin: 0 0;
  transform: rotate(45deg);
  background: #454144;
  z-index: 0;
}

.unit-progress {
  position: relative;
  border-radius: 22px;
  background: linear-gradient(180deg, #454144 0, #1e1e1e 100%);
  z-index: 1;
}

.uprogress__title {
  margin: 32px 0 40px;
  color: #fff;
  font-size: 0;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  text-align: center;
}

.uprogress__title span {
  display: inline-block;
  vertical-align: middle;
  font-size: 32px;
}

.uprogress__title--red {
  color: #f3535c;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}

/* 进度条 */
.uprogress__bar__wrapper {
  position: relative;
  margin-left: 30px;
  padding: 58px 0 76px;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
}

.uprogress__bar__container {
  padding-right: 30px;
  box-sizing: content-box;
}

.uprogress__bar {
  height: 10px;
  border-radius: 5px;
  background: rgba(242, 242, 242, 0.5);
  z-index: 0;
}

.uprogress__bar--cur {
  min-width: 10px;
  height: 10px;
  border-radius: 5px;
  background: #f97162;
}

.uprogress__steps {
  color: #fff;
  font-size: 20px;
}

.ups__desc,
.uprogress__step {
  position: absolute;
  top: 0;
}

.ups__desc__top,
.ups__top {
  height: 36px;
  line-height: 36px;
  white-space: nowrap;
}

.ups__desc__bottom,
.ups__bottom {
  margin-top: 45px;
}

.uprogress__step {
  transform: translateX(-50%);
  background: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAaBAMAAABbZFH9AAAAMFBMVEUAAABEQEREQkRFQURFQERFQURFQkRFQUM8PDzt7e1FQUTV1NV7eXvk5OSxsLGgnp8kZ57KAAAACXRSTlMAvjD45ryTgRGm9y0eAAAAnUlEQVQY02MAAXURY8ciBihQXQUCQRAO2yoISABxOKRWrXl9d9+pVQsbgDzGVWt2zpw5c/apVQJAXtaqnzNBYP6qZQwMTKvWz4SAX6sUGFhXnYTy5qwKYNBatRPKm71qEUPVmpkwcGo5g9Q6OO/VQgav1XDeriUMVmvhvFuLUXmoKlFNQbUB1XZUl6G6GsVHqL7FCAlEKKGHIGroAgCVJ6Wflcp3rwAAAABJRU5ErkJggg==')
    no-repeat center 50px/26px 26px;
}

.step--finish {
  background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABoAAAAaCAMAAACelLz8AAAAeFBMVEUAAABEQERFQURFQERFQURFQkRFQUNGQUZDQ0M8PDzzU1xFQUT////qUlvbUFjZUFi1TFOjSlF/R0x8RktIQUT96On0ZW3+9PX97/D83t/709X3lZr0anL++vv6xsn6xcj5s7f4qK34naL2i5H2hIr1eoH0bXXzWmJFGUKJAAAACnRSTlMAvvjmvJOBMy4RVimyMgAAANNJREFUKM+FklcSgzAMBWmhSKJ3SK/3v2GkDDgGBtgPjL1jzbMtY8R3TduybNP1jSmegwrH080BJxyUCEyeFlkSh2GcZAVPzGBQYvIIBqJc3L9aChrpWNNTZuIki8PVYAbXdPg8nCCaq4iz+IaLmMGCDNGVeIm29irLIw+JhLQRYxAq+fQnojuPMaJtWIghMBfqKrgSUSO7QkRLqZqo7Ni0FQxKFezpx/kDMBZUMZ41m5v8DTG08O+2eejhN468flEb17v+KOtPud8Ay7bZa7aNFv0Cl70YlJfACxkAAAAASUVORK5CYII=');
}

.ups__top {
  position: relative;
  padding: 0 6px;
  border-radius: 10px;
  background: #a3a1a2;
  box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.1);
}

.ups__top:after {
  content: '';
  position: absolute;
  top: 36px;
  left: 0;
  width: 100%;
  height: 10px;
  background: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACYAAAAKBAMAAAAqfTHQAAAAIVBMVEUAAAAAAACjoaIAAAAAAACioKGhoaGdnZ2ZlpaQkJBzc3OTRMGuAAAAC3RSTlMAA/4HC/R3aFpOKsPQ4BAAAAA/SURBVAjXY4CCJCUlJTUGFMAoDhQrFEAVE25VijBEF/MMnYIh5rLKBU2MQdjExdkQSKMqNIYpQwBBQUEGEgEAF0kICvJDMw8AAAAASUVORK5CYII=')
    no-repeat center/contain;
}

.step--finish .ups__top {
  background: #f3535c;
}

.step--finish .ups__top:after {
  background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAKBAMAAAAnY0GXAAAAIVBMVEUAAAAAAAAAAAD0U1zyU1zyUVzrUVjjTFXYSFKwPUPzU1wI4D6QAAAACnRSTlMABgr49HdoWk4qKeKxkwAAADxJREFUCNdjAAPWVUAQwIAAjFmrVi0TQBYQt1pciCIg1OKhiCqgOQlFgEFQSUkQRCOUCApCFCBEYHzCAAD9uwmiV8tmdQAAAABJRU5ErkJggg==');
}

.ups__bottom {
  text-align: center;
}

/* 按钮 */
.nb__btn {
  display: block;
  margin-top: 20px;
  height: 80px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  text-align: center;
  border-radius: 40px;
  box-sizing: border-box;
}

.btn__join {
  color: #fff;
  font-size: 32px;
  line-height: 80px;
  background: linear-gradient(180deg, #fe667e 0, #ff5950 100%);
  box-shadow: 0 9px 10px 0 #ffe4e5;
}
</style>

<template>
  <div class="page bgc-wt cfix">
    <navigator v-for="(info, i) in groupInfoList" :key="i" class="section unit-section" :url="info.groupUnit.unitUrl">
      <div class="unit-item">
        <div v-if="info.groupUnit.unitBadge" class="unit-badge" :style="{ backgroundImage: 'url(' + info.groupUnit.unitBadge + ')' }"></div>
        <div class="uitem__image" :style="{ backgroundImage: 'url(' + info.item.picMediaList[0]['picUrl'] + ')' }"></div>
        <div class="uitem__main">
          <p class="uitem__name line line-2">
            <span class="uitem__name__txt">{{ info.item.name }}</span>
          </p>
          <p class="uitem__status">
            <!-- 开团 -->
            <template v-if="!info.end && info.countdown && info.countdown.length">
              <p v-for="(cd, j) in info.countdown" :key="j" class="cd">{{ cd }}</p>
              <p class="cd__subfix">后结束</p>
            </template>
            <!-- 截团 -->
            <template v-if="info.groupUnit.unitStatus === 'FINISH'">
              <p class="finish__time">截团时间：{{ info.groupUnit.finishTime }}</p>
            </template>
          </p>
          <div class="uitem__price">￥{{ info.item.sellPrice }}</div>
        </div>
      </div>

      <div class="unit-progress__wrapper">
        <div class="unit-progress cfix">
          <div v-if="info.groupUnit.unitTitle" class="uprogress__title">
            <span v-for="t in info.groupUnit.unitTitle" :class="'uprogress__title--' + t.type" :key="$index">{{ t.txt }} </span>
          </div>
          <div v-if="info.groupUnit.progressBar" class="uprogress__bar__wrapper cfix">
            <div class="uprogress__bar__container" :style="{ width: info.groupUnit.progressBar.totalWidth }">
              <div class="uprogress__bar" :style="{ width: info.groupUnit.progressBar.totalWidth }">
                <div class="uprogress__bar--cur" :style="{ width: info.groupUnit.progressBar.curWidth }"></div>
              </div>
            </div>

            <div class="uprogress__steps">
              <div class="ups__desc">
                <p class="ups__desc__top">阶梯价</p>
                <p class="ups__desc__bottom">已团</p>
              </div>
              <div v-for="(step, k) in info.groupUnit.progressBar.steps" :key="k" class="uprogress__step" :style="{ left: step.left }" :class="step.cls">
                <p class="ups__top">{{ step.payPrice }}</p>
                <p class="ups__bottom">{{ step.numName }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="unit-buttons">
        <div class="nb__btn btn__join">
          我要参团
        </div>
      </div>
    </navigator>
  </div>
</template>

<script>
// import initMixin from 'mixins/init'
// import Tools from 'utils/tools'
// import { getStructArr } from 'utils/textStruct'

const getProgressBar = unit => {
  const PANEL_WIDTH = ((document.body.clientWidth || document.documentElement.clientWidth) * 570) / 750
  const PER_WIDTH = (PANEL_WIDTH * 120) / 570
  const LIMIT = 4
  if (!unit || !unit.currSkuDiscount) return null
  // 阶梯
  let steps = [...unit.currSkuDiscount]

  let stepLength = steps.length
  let skuNum = unit.skuNum
  let perStepWidth = steps.length > LIMIT ? PER_WIDTH : PANEL_WIDTH / (stepLength + 1)
  let totalWidth = stepLength <= LIMIT ? PANEL_WIDTH : (stepLength + 1) * perStepWidth
  steps.map((step, i) => {
    step.left = (i + 1) * perStepWidth + 'px'
    if (skuNum >= step.num) {
      step.cls = 'step--finish'
    }
    return step
  })
  // 计算当前的进度
  let curWidth = 0,
    nextNum,
    nextPrice
  if (skuNum > steps[stepLength - 1]['num']) {
    curWidth = (stepLength + 0.3) * perStepWidth
  } else {
    for (let i = 0; i < stepLength; i++) {
      let step = steps[i]
      if (skuNum > step.num) {
        curWidth += perStepWidth
      } else {
        let curNum = step.num
        if (skuNum === step.num) {
          let nextStep = steps[i + 1]
          nextNum = nextStep && nextStep.num - skuNum
          nextPrice = nextStep && nextStep.payPrice
        } else {
          nextNum = curNum - skuNum
          nextPrice = step.payPrice
        }
        let prev = steps[i - 1] ? steps[i - 1]['num'] : 0
        let w = ((skuNum - prev) / (curNum - prev)) * perStepWidth
        curWidth += w
        break
      }
    }
  }
  return {
    totalWidth: `${totalWidth}px`,
    curWidth: `${curWidth}px`,
    steps,
    nextNum,
    nextPrice
  }
}

const getUnitBadge = unit => {
  if (!unit || !unit.unitStatus) return
  switch (unit.unitStatus) {
    case 'SUCCESS':
      return 'https://pic.bbtkids.cn/Fh8X_HivvqrPR2TjEkghNdILwwld'
    case 'OVERDUE':
      return 'https://pic.bbtkids.cn/FlH8G4dr9GYAb2RsxNtYe-twpVzC'
    case 'FINISH':
      return 'https://pic.bbtkids.cn/FstP5geGmL2fbH_qIKzCsJq2Cc2U'
  }
}

export default {
  data() {
    return {
      timer: null,
      groupInfoList: []
    }
  },
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  computed: {
    allEnd() {
      return this.groupInfoList.every(group => group.end)
    }
  },
  components: {},
  methods: {
    initCountdown() {
      if (this.allEnd) return
      if (this.timer) {
        clearInterval(this.timer)
        this.timer = null
      }
      let calcCountdown = this.calcCountdown.bind(this)
      calcCountdown()
      this.timer = setInterval(calcCountdown, 1000)
    },
    calcCountdown() {
      let now = (Date.now() / 1000) | 0

      this.groupInfoList = this.groupInfoList.map(group => {
        if (group.end) return group
        let end = group.groupUnit.endTime
        if (now >= end) {
          group.end = true
          group.countdown = ['00', '00', '00']
        } else {
          let _diff = end - now

          let _h = ~~(_diff / 3600)
          let _m = ~~((_diff = _diff % 3600) / 60)
          let _s = _diff % 60
          _h = ('0' + _h).slice(-2)
          _m = ('0' + _m).slice(-2)
          _s = ('0' + _s).slice(-2)
          group.countdown = [_h, _m, _s]
        }
        if (this.allEnd) {
          clearInterval(this.timer)
          this.timer = null
        }

        return group
      })
    }
  },
  mixins: [initMixin],
  mounted() {
    this.groupInfoList = this.tplData.groupInfoList.map(info => {
      let unit = info.groupUnit || {}
      // 标
      unit.unitBadge = getUnitBadge(unit)
      // 进度
      unit.progressBar = getProgressBar(unit)
      // 完成时间
      unit.finishTime = Tools.timestampFormat(unit.endTime)

      // 进度条描述
      if (unit.discountTips) {
        unit.unitTitle = getStructArr(unit.discountTips)
      }

      info.groupUnit = unit
      info.end = !(unit.unitStatus === 'OPEN' || unit.unitStatus === 'SUCCESS')
      return info
    })

    this.initCountdown()
  }
}
</script>
