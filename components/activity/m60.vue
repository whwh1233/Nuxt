<style>
.m60 {
  margin: 0 20px 20px 20px;
  padding: 0 10px;
  border-radius: 50px;
  background-color: #fff;
  overflow: hidden;
}
.m60__ele {
  display: flex;
  align-items: center;
  padding: 20px 0;
}
.m60__ele__wrapper {
  display: block;
  border-bottom: 1px solid #eeeeee;
}
.m60__ele__wrapper:last-of-type {
  border: 0;
}
.m60__itempic {
  position: relative;
  margin-right: 20px;
  width: 240px;
  height: 240px;
  border-radius: 50px;
  overflow: hidden;
  background-size: contain;
  background-repeat: no-repeat;
  background-position: center;
}
.m60__item__modal {
  position: absolute;
  left: 0;
  top: 0;
  width: 240px;
  height: 240px;
  border-radius: 50px;
  background-color: #000000;
  opacity: 0.02;
}
.m60__item__soldout {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  margin: auto;
  width: 188px;
  height: 188px;
  border-radius: 50%;
  background-image: url('https://pic.bbtkids.cn/FqS8OuOlTgUs-dGWFFSO4N3n0LDm');
}
.m60__info {
  flex: 1;
  position: relative;
  height: 240px;
}
.m60__info__sell {
  display: flex;
  align-items: center;
}
.m60__sellpoint {
  display: block;
  margin-right: 16px;
  font-family: PingFangSC-Semibold;
  font-weight: 600;
}
.m60__tag {
  display: block;
  color: #f95555;
  padding: 2px 10px;
  font-size: 18px;
  border-radius: 4px;
  white-space: nowrap;
  background: #ffebec;
}
.m60__itemname {
  margin-top: 11px;
  color: #aaaaaa;
  font-size: 24px;
}
.m60__price {
  position: absolute;
  left: 0;
  bottom: 0;
}
.m60__sellprice {
  font-size: 42px;
  font-family: PingFangSC-Semibold;
  font-weight: 600;
}
.m60__sellprice::before {
  content: '';
  display: inline-block;
  width: 32px;
  height: 29px;
  background-image: url('https://pic.bbtkids.cn/FgsYooULfPIYmJjpCt0Yl4XUjPjb');
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
}
.m60__earnprice {
  color: #f95555;
  font-size: 26px;
}
.m60__count__btns {
  position: absolute;
  right: 0;
  bottom: 0;
  text-align: center;
}
.m60__single__btn {
  padding: 0 16px;
  height: 44px;
  font-size: 20px;
  line-height: 44px;
  text-align: center;
  border-radius: 22px;
  box-sizing: border-box;
}
.m60__soldout__btn {
  color: #888888;
  border: 1px solid rgba(136, 136, 136, 1);
}
.m60__pretext {
  margin-bottom: 18px;
  color: #f95555;
  font-size: 20px;
}
.m60__presold__btn {
  padding: 0 32px;
  height: 44px;
  color: #f95555;
  font-size: 20px;
  line-height: 44px;
  text-align: center;
  border: 1px solid rgba(249, 85, 85, 1);
  border-radius: 22px;
}
.m60__tob__buy__btn {
  display: inline-block;
  margin-right: 8px;
  color: #f95555;
  border: 1px solid rgba(249, 85, 85, 1);
}
.m60__tob__share__btn,
.m60__toc__buy__btn {
  display: inline-block;
  color: #fff;
  background: linear-gradient(135deg, rgba(252, 88, 78, 1) 0%, rgba(253, 86, 103, 1) 100%);
  box-shadow: 0 4px 12px 0 rgba(255, 118, 118, 0.54);
  background-repeat: repeat-y;
}
.m60__salesvolume {
  margin-top: 20px;
  color: #aaaaaa;
  font-size: 24px;
}
.m60__originprice {
  margin-left: -2px;
  color: #aaaaaa;
  font-size: 28px;
  font-family: PingFangSC-Regular;
  font-weight: normal;
  text-decoration: line-through;
}
.m60__nav__list {
  position: sticky;
  top: 0;
  display: flex;
  align-items: flex-end;
  margin-top: 10px;
  padding: 20px 30px 20px 30px;
  white-space: nowrap;
  box-sizing: content-box;
  z-index: 1000;
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
}
.m60__nav__ele {
  margin-right: 16px;
  padding: 0 16px;
  height: 52px;
  font-size: 22px;
  line-height: 52px;
  border-radius: 17px;
  color: #888888;
  background: #f2f2f2;
}
.m60__nav__ele--active {
  color: #fd5853;
}
</style>
<template>
  <div>
    <div class="m60__nav__list" v-if="tplData.tabList.length > 0" :style="{ background: activityInfo.baseCss && activityInfo.baseCss.bgcolor ? activityInfo.baseCss.bgcolor : '#FFF' }">
      <div class="m60__nav__ele" @click="changeTab($event, index)" :class="nav === chosedNav ? 'm60__nav__ele--active' : ''" v-for="(nav, index) in tplData.tabList" :key="index">
        {{ nav }}
      </div>
    </div>
    <div class="m60">
      <navigator
        :url="`/m/uiww/getSellItem?itemId=${item.itemId}`"
        :vc="`sellitemvc&itemId=${item.itemId}`"
        v-for="(item, index) in tplData.itemList"
        :key="index"
        class="m60__ele__wrapper"
        v-show="item.tab === chosedNav || chosedNav === 'singleAll'"
      >
        <div class="m60__ele">
          <div class="m60__itempic" :style="{ backgroundImage: 'url(' + item.picUrl + ')' }">
            <div class="m60__item__modal"></div>
            <div class="m60__item__soldout div-bg" v-if="item.soldOut"></div>
          </div>
          <div class="m60__info">
            <p class="m60__info__sell" v-if="item.sellingPoint || item.tag">
              <span class="m60__sellpoint line line-1" v-if="item.sellingPoint">{{ item.sellingPoint }}</span>
              <span class="m60__tag" v-if="item.tag">{{ item.tag }}</span>
            </p>
            <p class="m60__itemname line" :class="item.sellingPoint || item.tag ? 'line-1' : 'line-2'">{{ item.name }}</p>
            <p class="m60__salesvolume" v-if="item.salesNum">已售: {{ item.salesNum }}</p>
            <div class="m60__price">
              <p class="m60__sellprice">
                {{ item.predictPrice || item.sellPrice }} <span class="m60__originprice" v-if="item.originPrice">￥{{ item.originPrice }}</span>
              </p>
              <p class="m60__earnprice" v-if="item.rebate">返{{ item.rebate }}</p>
            </div>
            <div class="m60__count__btns">
              <template v-if="item.soldOut">
                <div class="m60__soldout__btn m60__single__btn">已售罄</div>
              </template>
              <template v-else-if="item.countTime && item.countTime.start > item.countTime.current">
                <count-down :ref="item.itemId" :time-obj="item.countTime">
                  <template v-if="diffObj[item.itemId]">
                    <p v-if="diffObj[item.itemId].period === 0" class="m60__pretext">距离开始{{ diffObj[item.itemId]['time'] }}</p>
                    <div class="m60__presold__btn">{{ diffObj[item.itemId]['btnText'] }}</div>
                  </template>
                </count-down>
              </template>
              <template v-else>
                <template v-if="isMember">
                  <div class="m60__tob__buy__btn m60__single__btn">自买省</div>
                  <div class="m60__tob__share__btn m60__single__btn">分享赚</div>
                </template>
                <template v-else>
                  <div class="m60__toc__buy__btn m60__single__btn">立即抢购</div>
                </template>
              </template>
            </div>
          </div>
        </div>
      </navigator>
    </div>
  </div>
</template>
<script>
// import bridge from 'utils/bridge'
// import API from 'api/api'
export default {
  data() {
    return {
      refs: null,
      chosedNav: (this.tplData.tabList.length > 0 && this.tplData.tabList[0]) || 'singleAll',
      loadObj: {},
      loadingTab: false,
      paramNav: '',
      qcItemList: [] //数据更新去重处理
    }
  },
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    },
    activityInfo: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  computed: {
    diffObj() {
      let obj = {}
      if (this.refs) {
        this.tplData.itemList.forEach(item => {
          let itemId = item.itemId
          if (this.refs[itemId]) {
            let diff = this.refs[itemId][0].diffObj
            let time = new Date(item.countTime.start * 1000)
            obj[itemId] = {}
            obj[itemId]['period'] = this.refs[itemId][0].period
            obj[itemId]['time'] = `${diff.H}:${diff.m}:${diff.s}`
            obj[itemId]['btnText'] = `${time.getDate()}日${time.getHours()}点开抢`
          }
        })
      }
      return obj
    },
    param() {
      return {
        mode: 'getTabItemList',
        actid: this.$parent.activityInfo.id,
        connid: this.tplData.connId,
        tab: this.paramNav
      }
    }
  },
  components: {
    // countDown
  },
  methods: {
    formateItemList() {
      let itemDict = {}
      this.tplData.itemList.forEach((item, index) => {
        itemDict[item.itemId] = index
        this.qcItemList.push(item.itemId + '_' + item.tab)
      })
      this.tplData.countList.forEach(count => {
        count['itemIds'].forEach(itemId => {
          this.$set(this.tplData.itemList[itemDict[itemId]], 'countTime', count['countTime'])
        })
      })
      this.$nextTick(() => {
        this.refs = this.$refs
      })
    },
    async changeTab(e, index) {
      this.paramNav = this.tplData.tabList[index]
      if (!this.loadObj[this.paramNav]) {
        if (!this.loadingTab) {
          this.loadingTab = true
          let res = await this.request.post(API.actgetdata, this.param)
          if (res.data.errno === 0) {
            this.loadObj[this.paramNav] = true
            this.loadingTab = false
            let data = res.data.data
            if (this.qcItemList.indexOf(data.itemList[0].itemId + '_' + data.itemList[0].tab) === -1) {
              this.tplData.itemList = this.tplData.itemList.concat(data.itemList)
              this.tplData.countList = this.tplData.countList.concat(data.countList)
              this.formateItemList()
            }
          }
        }
      }
      this.chosedNav = this.paramNav
      console.log(this.chosedNav)
    }
  },
  created() {
    this.formateItemList()
    this.tplData.tabList.forEach((tab, index) => {
      this.loadObj[tab] = index === 0 ? true : false
    })
  },
  mounted() {
    this.refs = this.$refs
  }
}
</script>
