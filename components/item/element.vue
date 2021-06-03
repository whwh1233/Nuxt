<style scoped>
.item-element {
  position: relative;
  padding-bottom: 20px;
  text-align: center;
  background: #fff;
}

.act-img__wrapper {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
}

.act__img {
  display: block;
  width: 100px;
}

/* .arui__wrapper {
  border: 4px solid #e34f59;
  border-bottom: 0;
} */

.item__img {
  position: relative;
  height: 0;
  border-radius: 12px 12px 0 0;
  padding-bottom: 133.3333%;
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
  overflow: hidden;
}

.item__img:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  border-radius: 12px 12px 0 0;
  background: rgba(0, 0, 0, 0.02);
  z-index: 1;
}

.activity {
  position: absolute;
  left: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 10px;
  width: 100%;
  height: 50px;
  color: #fff;
  box-sizing: border-box;
  background-color: #f95555;
  background-image: linear-gradient(to right, #f95555, #ff4974);
}

/* .aruidacu__act-panel {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: calc(16.267vw - 50px) 10px 0;
  width: auto;
  height: 16.267vw;
  color: #fff;
  box-sizing: border-box;
  background: url('https://pic.bbtkids.cn/FhRlsZI46isVYfnkjmryOncch6BE') no-repeat center/100% 100%;
  z-index: 1;
} */

.activity__name {
  margin-right: 22px;
  font-size: 18px;
  line-height: 1.2;
  text-align: left;
}

.activity__price {
  font-size: 32px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
}

.brand-name {
  margin: 12px 15px 0;
  color: #aaa;
  font-size: 24px;
}

.item-name {
  margin: 4px 15px 0;
  height: 74px;
  font-size: 26px;
  line-height: 37px;
}

.item-price-section {
  display: flex;
  align-items: center;
  justify-content: center;
}

.b-sellprice {
  padding-right: 5px;
}

.b-line {
  margin: 0 9px 0 5px;
  width: 2px;
  height: 22px;
  background: #eee;
}

.b-profit {
  padding-top: 2px;
  color: #f95555;
  font-size: 25px;
}

.c-sellprice {
  color: #f95555;
}

.c-originprice {
  margin-left: 10px;
  color: #888;
  text-decoration: line-through;
}

.c-discount {
  margin-left: 10px;
  padding: 0 10px;
  color: #fff;
  font-size: 22px;
  line-height: 32px;
  background: #f95555;
}

.bi__item__soldout-img,
.bi__item__remain-img {
  position: absolute;
  top: 108px;
  left: 0;
  right: 0;
  margin: auto;
  width: 244px;
  height: 244px;
  z-index: 80;
  background-size: contain;
}

.icon__list {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  height: 30px;
  margin-top: 4px;
  margin-bottom: 4px;
}

.tip-icon {
  height: 30px;
}

.saled {
  margin: 4px auto 6px;
  color: #aaa;
  height: 38px;
  font-size: 26px;
  line-height: 38px;
}

.navigator__span {
  display: block;
}

.presale-panel {
  width: 100%;
  height: 50px;
  background: #111 url('https://pic.bbtkids.cn/Fn-Tf24Ey4V98DZF_JgAuu7IGA_j') no-repeat center/contain;
  display: flex;
  flex-direction: column;
  color: #fff;
  padding-left: 14px;
  position: absolute;
  bottom: 0px;
}

.presale__price {
  font-size: 24px;
  font-family: PingFangSC-Semibold, PingFangSC;
  font-weight: 600;
  text-align: left;
}

.presale__price:after {
  content: '预售价';
  width: 44px;
  height: 18px;
  font-size: 12px;
  font-family: PingFangSC-Regular, PingFangSC;
  font-weight: 400;
  border-radius: 4px;
  border: 1px solid rgba(255, 255, 255, 1);
  margin-left: 10px;
  text-align: center;
  display: inline-block;
  vertical-align: 4px;
  line-height: 16px;
  box-sizing: border-box;
}

.step__price {
  font-size: 14px;
  display: flex;
  align-items: center;
  margin-top: -8px;
}

.front__price {
  margin-right: 22px;
}

.hand-panel {
  width: 100%;
  position: absolute;
  bottom: 0px;
}

.btom100 {
  bottom: 50px;
}

.hand__top {
  width: 100%;
  height: 0px;
  padding-bottom: 15.61%;
  display: flex;
  position: relative;
}

.hand__left {
  width: 43.35%;
  height: 0px;
  padding-bottom: 15.61%;
  background: url('https://pic.bbtkids.cn/Fh24NytPGK9cZm5zgMpUWQ39Q9m6') no-repeat center/cover;
  position: relative;
}

.hand__right {
  width: 56.64%;
  height: 0px;
  padding-bottom: 9.24%;
  background: url('https://pic.bbtkids.cn/Fta2GzriC1832hnzCw7A2PK0QYxj') no-repeat left bottom/cover;
  position: absolute;
  bottom: 0px;
  right: 0px;
}

.left__detail {
  width: 94%;
  color: #fff;
  text-align: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  margin-top: 1.5%;
}

.hand__tag {
  font-size: 14px;
  line-height: 1;
}

.hand__price {
  font-size: 28px;
  font-family: PingFangSC-Semibold, PingFangSC;
  font-weight: 600;
  line-height: 1;
}
</style>

<template>
  <div class="item-element">
    <navigator class="navigator__span" v-bind="$attrs" v-on="$listeners" :url="itemUrl" data-emergence="hidden" :self-data="selfData" :prefix="pageType">
      <template v-if="item.soldOut">
        <div class="bi__item__soldout-img"></div>
      </template>
      <template v-else>
        <div v-if="itemReady" class="bi__item__remain-img"></div>
      </template>

      <div v-if="item.activityPicList" class="act-img__wrapper">
        <img class="act__img" v-for="pic in item.activityPicList" :src="pic.picUrl" />
      </div>
      <div class="item__img" :style="{ backgroundImage: 'url(' + item.picUrl + ')' }">
        <!-- 到手价 -->
        <div class="hand-panel" v-if="item.handPriceBanner" :class="{ btom100: item.presale || item.activityName }">
          <div class="hand__top">
            <div class="hand__left">
              <div class="left__detail">
                <p class="hand__tag line line-1">{{ item.handPriceBanner.handPriceTag }}</p>
                <p class="hand__price line line-1">{{ item.handPriceBanner.handPrice }}</p>
              </div>
            </div>
            <div class="hand__right"></div>
          </div>
        </div>
        <!-- 预售 -->
        <template v-if="item.presale">
          <div class="presale-panel">
            <p class="presale__price">{{ item.presale.sellPrice }}</p>
            <div class="step__price">
              <p class="front__price">定金 {{ item.presale.frontPrice }}</p>
              <p class="front__price">尾款 {{ item.presale.endPrice }}</p>
            </div>
          </div>
        </template>
        <!-- 红条 -->

        <div v-if="item.activityName" class="activity">
          <div class="activity__name">{{ item.activityName }}</div>
          <div v-if="item.predictPrice" class="activity__price">￥{{ item.predictPrice }}</div>
        </div>

        <!-- <div v-if="item.activityName" class="aruidacu__act-panel">
          <div class="activity__name">{{ item.activityName }}</div>
          <div v-if="item.predictPrice" class="activity__price">￥{{ item.predictPrice }}</div>
        </div> -->
      </div>

      <div v-if="item.brand" class="brand-name line line-1">
        {{ item.brand.name }}
      </div>
      <div class="line line-2 item-name">
        {{ item.name }}
      </div>
      <template v-if="item.itemTipsPic && item.itemTipsPic.length">
        <div class="icon__list line line-1" v-if="item.itemTipsPic && item.itemTipsPic.length">
          <img v-for="(icon, iconIndex) in item.itemTipsPic" :key="iconIndex" class="tip-icon" :src="icon.picUrl" alt="" />
        </div>
      </template>
      <template v-else>
        <p class="saled">
          <template v-if="item.salesNum">{{ item.salesNum }}</template>
        </p>
      </template>

      <div class="item-price-section" v-if="item.rebate">
        <div class="b-sellprice">￥{{ item.sellPrice }}</div>
        <div class="b-line"></div>
        <div class="b-profit">返{{ item.rebate }}</div>
      </div>

      <div v-else class="item-price-section">
        <div class="c-sellprice">￥{{ item.sellPrice }}</div>
        <template v-if="item.sellPrice !== item.originPrice">
          <div class="c-originprice">￥{{ item.originPrice }}</div>
          <div class="c-discount">{{ item.discount }}折</div>
        </template>
      </div>
    </navigator>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selfData: ''
    }
  },
  props: {
    item: {
      type: Object,
      default() {
        return {}
      }
    },
    index: {
      type: String,
      default() {
        return ''
      }
    },
    pageType: {
      type: String,
      default() {
        return ''
      }
    }
  },
  computed: {
    itemUrl() {
      if (this.item.goalUri) {
        return this.item.goalUri
      }
      if (this.item.itemUrl) {
        return this.item.itemUrl
      }
      if (this.isApp) {
        return `openvc://?vc=sellitemvc&itemId=${this.item.itemId}`
      }
      return `/m/uiww/getSellItem?itemId=${this.item.itemId}`
    },
    itemReady() {
      if (!this.item) return
      return this.item.itemStatus && this.item.itemStatus.toLowerCase() === 'ready'
    }
  },
  mounted() {
    let selectorList = this.$root.$children[0].selectorList
    let orderBy = this.$root.$children[0].orderBy
    if (selectorList && selectorList.length > 0) {
      var filter = JSON.stringify(selectorList)
    }
    let query = this.$root.$children[0].query
    let frontCategoryId = this.$root.$children[0].frontCategoryId
    let tag = this.$root.$children[0].tag
    let obj = {
      eleType: 'item',
      itemId: this.item.itemId,
      realItemId: this.item.realItemId || 0,
      index: this.index,
      logId: this.item.logId
    }
    if (this.item.predictPrice) {
      obj.predictPrice = this.item.predictPrice
    }
    if (filter) {
      obj.filter = filter
    }
    if (orderBy) {
      obj.orderBy = orderBy
    }
    if (query) {
      obj.query = query
    }
    if (frontCategoryId) {
      obj.frontCategoryId = frontCategoryId
    }
    if (tag) {
      obj.tag = tag
    }
    if (this.item.itemFeature === 'wwGroup') {
      obj.eleType = 'groupItem'
      let groupId = ''
      if (this.isApp) {
        groupId = this.urlUtil.getParam('groupId', '?' + decodeURIComponent(this.item.goalUri.split('url=')[1]).split('?')[1])
      } else {
        groupId = this.urlUtil.getParam('groupId', '?' + this.item.goalUri.split('?')[1])
      }
      obj.groupId = groupId
    }
    this.selfData = JSON.stringify(obj)
    // this.item.itemTipsPic = [
    //   { picUrl: 'https://pic.bbtkids.cn/Flwz6QWk1N92apFCUz76JjUKvEz4' },
    //   { picUrl: 'https://pic.bbtkids.cn/Flwz6QWk1N92apFCUz76JjUKvEz4' },
    //   { picUrl: 'https://pic.bbtkids.cn/Flwz6QWk1N92apFCUz76JjUKvEz4' },
    //   { picUrl: 'https://pic.bbtkids.cn/Flwz6QWk1N92apFCUz76JjUKvEz4' },
    // ]
    // this.item.activityName = 'hahahhahhah'
  }
}
</script>
