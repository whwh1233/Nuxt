<style scoped>
.wrapper {
  display: flex;
}

.img__wrapper {
  position: relative;
  margin-right: 24px;
  width: 240px;
  height: 240px;
}
.handprice__wrapper {
  position: absolute;
  left: 0px;
  bottom: 0px;
  width: 148px;
  height: 50px;
  color: #fff;
  background: rgba(0, 0, 0, 1);
  border-radius: 0 50px 0 50px;
  z-index: 100;
  text-align: center;
  line-height: 1;
  padding-top: 8px;
}
.hand__p--top {
  font-size: 14px;
}
.hand__p--bottom {
  font-size: 24px;
  font-family: PingFangSC-Semibold, PingFangSC;
  font-weight: 600;
}
.act-imgs {
  position: absolute;
  top: 0;
  left: 0;
  width: 90px;
  z-index: 2;
}

.bi__item__soldout-img,
.bi__item__remain-img {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
  width: 90px;
  height: 90px;
  z-index: 80;
  background-size: contain;
}

.img {
  position: relative;
  width: 100%;
  height: 100%;
  border-radius: 50px;
  background: no-repeat center/contain;
}

.img:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  border-radius: 50px;
  background: rgba(0, 0, 0, 0.02);
  z-index: 1;
}

.item {
  flex: 1;
}

.item__name {
  height: 33px;
  color: #555;
  font-size: 24px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
}

.predict__wrapper {
  margin-top: 10px;
  height: 75px;
  font-size: 0;
  overflow: hidden;
}
.presale__wrapper {
  height: 34px;
  display: flex;
  align-items: center;
  background: #111 url('https://pic.bbtkids.cn/FvwlMWsvmQXfD-p76hxMHz8xr4rt') no-repeat center right/contain;
  padding-left: 10px;
  border-radius: 8px;
}
.predict {
  display: inline-block;
  padding: 0 10px;
  height: 34px;
  color: #fc5752;
  font-size: 18px;
  line-height: 34px;
  border-radius: 8px;
  background: #ffebec;
}
.icon__list {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
  height: 30px;
  margin-top: 44px;
}
.tip-icon {
  height: 30px;
}
.predict + .icon__list {
  margin-top: 10px;
}
.price-panel {
  display: flex;
  align-items: center;
  margin-top: 10px;
}
.sellprice {
  padding-left: 32px;
  font-size: 34px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
  background: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACAAAAAdCAMAAAD8QJ61AAAAZlBMVEX///8AAACBgYGDg4ONjY0eHh6lpaUTExMNDQ2goKBQUFA1NTUwMDD8/Pz6+vrr6+vh4eHZ2dnR0dHGxsaxsbGRkZF7e3t4eHhkZGRTU1NHR0dCQkIbGxsEBASoqKhaWlo9PT0mJiZCclbGAAAAoElEQVQoz+XOyQ6CQBRE0bqNzDgrMw7//5PSMYSEbmLiwo1nU/WSWjz9l5MxwXwFxpy0EEM09QhiLUXQT723Y0cO13e7Qi7XGZKdLbsEzvJooLRZQiOfAwx7aT/AQV4V1FINlfy2MRyPEG+1IoUsg1SrCoBCfvcwDBOAZCyZXA+YFVphwMj6ZnDZjFpobV7kymH2lOsWjDrobKYff/jl4AUVJATrvzHwuQAAAABJRU5ErkJggg==')
    no-repeat left 8px/32px 29px;
}

.originprice {
  margin: 7px 0 0 8px;
  color: #aaa;
  font-size: 24px;
  text-decoration: line-through;
}

.rebate {
  margin: 3px 0 0 15px;
  color: #f95555;
  font-size: 24px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
}

.discount {
  margin-left: 8px;
  padding: 0 8px;
  height: 28px;
  color: #fff;
  font-size: 20px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  border-radius: 8px;
  background: #f95555;
}

.footer {
  display: flex;
  align-items: center;
  margin-top: 20px;
}

.saled {
  flex: 1;
  color: #aaa;
  font-size: 24px;
}

.btn-sellgroup {
  width: 90px;
  height: 44px;
  color: #fff;
  font-size: 20px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  line-height: 44px;
  text-align: center;
  border-radius: 22px;
  background: linear-gradient(180deg, #ff9f74 0, #fe5f3a 100%);
  box-shadow: 0 4px 6px 0 #ffd0c0;
}

.btn {
  height: 44px;
  font-size: 20px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  text-align: center;
  border-radius: 22px;
  box-sizing: border-box;
}

.buy {
  width: 90px;
  color: #f95555;
  line-height: 42px;
  border: 1px solid #f95555;
}

.share {
  margin-left: 8px;
  width: 90px;
  color: #fff;
  line-height: 44px;
  background: linear-gradient(135deg, rgba(252, 88, 78, 1) 0%, rgba(253, 86, 103, 1) 100%);
  box-shadow: 0 4px 12px 0 rgba(255, 118, 118, 0.54);
}

.buynow {
  width: 130px;
  color: #fff;
  line-height: 44px;
  background: linear-gradient(135deg, rgba(252, 88, 78, 1) 0%, rgba(253, 86, 103, 1) 100%);
  box-shadow: 0 4px 12px 0 rgba(255, 118, 118, 0.54);
}
.presale__price {
  color: #f2d8a9;
  font-size: 24px;
  font-family: PingFangSC-Medium, PingFangSC;
  font-weight: 500;
}
.presale__price:after {
  content: '预售价';
  display: block;
  color: #f3d2a3;
  font-size: 12px;
  display: inline-block;
  vertical-align: 4px;
  margin-left: 4px;
}
.front__price,
.end__price {
  color: #ffffff;
  font-size: 16px;
}
.front__price {
  flex: 1;
  text-align: right;
  margin-right: 10px;
}
.end__price {
  margin-right: 24%;
}
</style>

<template>
  <div class="item-element-single">
    <navigator class="wrapper" v-bind="$attrs" v-on="$listeners" :url="itemUrl" data-emergence="hidden" :self-data="selfData" :prefix="pageType">
      <div class="img__wrapper">
        <div v-if="item.activityPicList && item.activityPicList.length" class="act-imgs">
          <img class="block-image" v-for="pic in item.activityPicList" :src="pic.picUrl" />
        </div>
        <div class="handprice__wrapper" v-if="item.handPriceBanner">
          <p class="hand__p--top">{{ item.handPriceBanner.handPriceTag }}</p>
          <p class="hand__p--bottom line line-1">{{ item.handPriceBanner.handPrice }}</p>
        </div>
        <template v-if="item.soldOut">
          <div class="bi__item__soldout-img"></div>
        </template>
        <template v-else>
          <div v-if="itemReady" class="bi__item__remain-img"></div>
        </template>
        <div class="img" :style="{ backgroundImage: 'url(' + item.picUrl + ')' }"></div>
      </div>

      <div class="item">
        <p class="item__name line line-1">{{ item.name }}</p>
        <!-- 红条和预售条容器 -->
        <div class="predict__wrapper" :class="{ presale__wrapper: item.presale }">
          <template v-if="item.presale">
            <p class="presale__price">{{ item.presale.sellPrice }}</p>
            <p class="front__price">定金 {{ item.presale.frontPrice }}</p>
            <p class="end__price">尾款 {{ item.presale.endPrice }}</p>
          </template>
          <template v-else>
            <p v-if="item.activityName" class="predict line line-1">{{ item.activityName }}</p>
            <div class="icon__list" v-if="item.itemTipsPic && item.itemTipsPic.length">
              <img v-for="(icon, iconIndex) in item.itemTipsPic" :key="iconIndex" class="tip-icon" :src="icon.picUrl" alt="" />
            </div>
          </template>
        </div>

        <div class="price-panel">
          <p class="sellprice">
            <template v-if="item.predictPrice">{{ item.predictPrice }}</template>
            <template v-else>{{ item.sellPrice }}</template>
          </p>
          <p v-if="showOriginPrice" class="originprice">{{ item.originPrice }}</p>
          <p v-if="item.rebate" class="rebate">返{{ item.rebate }}</p>
          <p v-else-if="item.discount" class="discount">{{ item.discount }}折</p>
        </div>

        <div class="footer">
          <p class="saled">
            <template v-if="item.salesNum">{{ item.salesNum }}</template>
          </p>
          <template v-if="item.groupItem">
            <div class="btn-sellgroup">去开团</div>
          </template>
          <template v-else>
            <template v-if="isMember">
              <div class="btn buy">自买省</div>
              <div class="btn share">分享赚</div>
            </template>
            <template v-else>
              <div class="btn buynow">立即抢购</div>
            </template>
          </template>
        </div>
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
      if (this.isApp) {
        return `openvc://?vc=sellitemvc&itemId=${this.item.itemId}`
      }
      return `/m/uiww/getSellItem?itemId=${this.item.itemId}`
    },
    itemReady() {
      if (!this.item) return
      return this.item.itemStatus && this.item.itemStatus.toLowerCase() === 'ready'
    },
    showOriginPrice() {
      return this.item.sellPrice !== this.item.originPrice
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
    // this.item.presale = {
    //   startTime: '2019.11.10 10:00',
    //   endTime: '2019.11.10 10:00',
    //   startPrice: '10',
    //   endPrice: '89',
    //   state: 1,
    //   isStart: true,
    //   contentText: "1",
    //   deliverText: "付尾款后7天内发货",
    //   frontPrice: "¥10",
    //   sellPrice: '¥8888',
    //   originPrice: '¥9999'
    // }
    // this.item.handPriceBanner = {
    //   handPriceTag: '最终到手价',
    //   handPrice: '999.9',
    //   formula: '到手价=售价￥169-活动优惠￥20-优惠券￥10-分润(双倍)￥5x2',
    //   handPriceNotice: 'TIME:11.1 00:00-11.12 24:00'
    // }
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
