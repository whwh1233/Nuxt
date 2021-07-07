<style scoped>
.m55 {
  padding: 0px 20px;
  box-sizing: border-box;
}

.m55__wrapper {
  position: relative;
  margin: 0 10px 10px 0;
  border-radius: 32px;
  background: #fff;
  overflow: hidden;
}

.m55__wrapper.m55__wrapper--1 {
  display: flex;
  align-items: center;
  margin-right: 0;
}

.m55__wrapper.m55__wrapper--2 {
  float: left;
  width: calc(50% - 5px);
}

.m55__wrapper.m55__wrapper--2:nth-of-type(2n + 2) {
  margin-right: 0;
}

.m55__wrapper.m55__wrapper--3 {
  float: left;
  width: calc(33.3333% - 6.6667px);
}

.m55__wrapper.m55__wrapper--3:nth-of-type(3n + 3) {
  margin-right: 0;
}

.m55__img {
  position: relative;
  background: no-repeat center/contain;
  overflow: hidden;
}

.m55__img:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.02);
  z-index: 1;
}

.m55__wrapper--1 .m55__img {
  width: 350px;
  height: 350px;
  border-radius: 32px 0 0 32px;
}

.m55__wrapper--2 .m55__img,
.m55__wrapper--3 .m55__img {
  padding-bottom: 100%;
  width: 100%;
  height: 0;
  border-radius: 32px 32px 0 0;
}

.m55__wrapper--1 .m55__item {
  flex: 1;
  padding: 24px 20px 26px;
  height: 350px;
}

.m55__wrapper--2 .m55__item {
  padding: 24px 24px 32px;
}

.m55__wrapper--3 .m55__item {
  padding: 16px 16px 26px;
}

.m55__wrapper--1 .m55__name {
  height: 80px;
  line-height: 40px;
}

.m55__wrapper--2 .m55__name {
  margin-bottom: 16px;
  height: 72px;
  font-size: 24px;
  text-align: center;
}

.m55__wrapper--3 .m55__name {
  margin-bottom: 11px;
  height: 66px;
  font-size: 22px;
  text-align: center;
}

.m55__tag__wrapper {
  margin-top: 16px;
  height: 34px;
}

.m55__tag {
  display: inline-block;
  padding: 3px 14px;
  color: #fff;
  font-size: 20px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  text-align: center;
  border-radius: 17px;
  background: #f95555;
  box-shadow: 0 2px 5px 0 rgba(255, 103, 103, 0.5);
}

.m55__wrapper--2 .m55__tag {
  position: absolute;
  right: 20px;
  top: 20px;
}

.m55__wrapper--3 .m55__tag {
  position: absolute;
  right: 10px;
  top: 10px;
  padding: 2px 10px;
  font-size: 18px;
  box-shadow: 0 2px 4px 0 rgba(255, 103, 103, 0.2);
}

.m55__price {
  display: flex;
  align-items: center;
}

.m55__wrapper--1 .m55__price {
  margin-top: 52px;
}

.m55__wrapper--2 .m55__price,
.m55__wrapper--3 .m55__price {
  justify-content: center;
}

.m55__sellprice {
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}

.m55__sellprice {
  font-size: 40px;
}

.m55__wrapper--3 .m55__sellprice {
  font-size: 32px;
}

.m55__sellprice:first-letter {
  margin-top: 11px;
  font-size: 24px;
}

.m55__wrapper--3 .m55__sellprice:first-letter {
  margin-top: 10px;
  font-size: 18px;
}

.m55__originprice {
  margin: 11px 0 0 8px;
  color: #aaa;
  font-size: 24px;
  text-decoration: line-through;
}

.m55__wrapper--3 .m55__originprice {
  margin-top: 7px;
  font-size: 20px;
}

.m55__btn {
  font-size: 0;
}

.m55__wrapper--1 .m55__btn {
  margin-top: 14px;
}

.m55__wrapper--2 .m55__btn {
  margin-top: 4px;
  text-align: center;
}

.m55__wrapper--3 .m55__btn {
  margin-top: 3px;
  text-align: center;
}

.m55__rabate {
  display: inline-block;
  padding: 0 15px 0 18px;
  height: 48px;
  color: #f95555;
  font-size: 24px;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: bold;
  line-height: 48px;
  border-radius: 24px;
  background: #fff5f5;
  overflow: hidden;
}

.m55__view {
  display: inline-block;
  width: 131px;
  height: 48px;
  background: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIMAAAAwCAMAAAAFHTmPAAAAwFBMVEUAAAD/9vb/9fX/8/P/9vb/9vb/9fX/9fX/9fX/9vb/9fX/9vb/+Pj/9/f/9vb/+Pj/8vL/+fn/////9fX5VVX/8vL/9PT/7+//6ur/39/6YWH/////8fH/5ub+29v5WFj9xMT/7Oz8l5f/4eH8oKD8nJz8kJD/4+P+z8/8kpL7iYn5XFz/5+f+1tb9vr77hIT7f3/6c3P6Zmb7jY36dnb9trb8pKT6a2v+6Oj9u7v9sbH8qKj6bm79ra39yMj6enoKk9GBAAAAE3RSTlMA84cT+vbl1MbAuXVnYlJHJhgCwL/DogAABGhJREFUWMPNmet2ojAQgNW1rbeq3QlyEVBAxftttVa37b7/W+0kASeCtn823X5nDwkHFj5nJgHSQo6nZqn2cH8H/567+4daqflU+IQfjWoH9NKpNn58ZFAqwldQLN2y+FnXbkAW9Z/XFNoV+Eoq7bxCqwhfS7GVVXgsg0Y6CaBSfswogDZQwDhzqXEh0dIXBRQw++HO6fWcXdg3UYOOlZV0tLXVAhrMBw474wzmqkWxfR6U2kYEKiylAVksVYlKOkTroAdUMAcsx8BUJOrJ7KgrE6gwZVeYKhJFOWOW4BLTtm0LJBH2OxZuTABsiBeTb4AT23YkOsl5pOAO2FUGLkmUroZhgWcNZdfH7homuF0AjJjCGz9rAMhLj7EDcNaMzSxV4chucBQSFIgGZJjjSb9k9xd2x7DBaxsAr0xhbKemv7GzFcLkzjEMj8pxMrksTM8wIKGBDtVcGnv4489hmIKJ+38AAqYSWLgJ+a22/JqADBnredfrcdLt9ns36rKKryxpnzgwthGdKV7Vh7H8fWPxX1PASByWDJnxMnLwXkoYXMtRHbrjmRoIyzVS2adCE3Ksk+AumLjqGzZLGfM+EMkt/6AnY9jZ43FfDcOSEXuU8B1GLCkQTRoVxAgv20nCEMuisMUeiy+jNRKea8yGCbDheVMdQqbwGyXiLe2H5FAq1CDHM57zQuPjIPO9xZD3E1AJdli5wrePxWqJVC3UVAQ7pjJECYvKeheck1ErPGQEKKpTvCmqvODeCsBjCn2ZsSl4PfbawQh4PFrrizCIciBQuNt1D1QQ50A8FO4hx7sYkQsewWTvGaDPFDw5bqc8ZCdeEjbKsPdLBxoIlI7zUOmRw33hDnL4oghXWJlmkpl32axGkhCQEPddh80CHhEfD+/gtgPFIe9wl3eQM8FpwTeArHh1yCYAhQEG/4h5FofGW66dy8XtenAUB8rF5bAb4IUPbrJzwIti8woqb+iwS0fMEI8aGYfdR+Nip+YiX5NimOE/+cMiOXPb2IyylTuTw3EkenvIOEw+mh8mak3mx6aMO2p0IJkH32Qz8BNsgLRIx6IykK2bdTiy3DxJHMmhlp+jkoumZT6UN8KGmAIyFp7yFOGZdYid288LJyaHUn6ulo9COdqTudjkDSHv54ufk1Qnc9J6pTlqTt7Z5yYbzmmOatIzS+Eoo8wxMIIb0RDyUMzvbKbz6jNALhBUAFkcn8LQeeLPbg0IB+90y+HkkUNVvMNowXBRIryuEKLCORUNDa+0FIhgHq2uKayieZCEIX2pLYEWDJ6NKLwShYhnIg1DCQ00BsLlEqfsN86JK7gUBm3fOCQRL0JHMQgXsaoAdX3feiQx9yJ/P9rwb97NaO9H3lxVqPzU981LEoHleVFkC6LI86xAUSi2dX7704e/aWEsvBjxMAaWqXz+l1ta10BIwjUxFgmBabqkAI+614LIAjUEQoAMyo+fr4lpXgsqtjSvDX6+JlZpf9M10m+xVvw91sz/098O/gKEtN2tZoWm4gAAAABJRU5ErkJggg==')
    no-repeat center/contain;
}

.m55__salenum {
  position: absolute;
  left: 0px;
  bottom: 0px;
  width: 148px;
  height: 40px;
  border-radius: 0px 40px 0px 0px;
  background: rgba(0, 0, 0, 0.5);
  color: #fff;
  font-size: 20px;
  font-family: PingFangSC-Regular, PingFangSC;
  font-weight: 400;
  text-align: center;
  line-height: 40px;
}

.m55__wrapper--1 .m55__salenum {
  width: 148px;
  height: 40px;
  line-height: 40px;
}

.m55__wrapper--2 .m55__salenum,
.m55__wrapper--3 .m55__salenum {
  width: 142px;
  height: 36px;
  line-height: 36px;
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
  font-family: PingFangSC-Semibold, PingFangSC, sans-serif, 'SimHei', 'Noto Sans SC';
  font-weight: 600;
  text-align: left;
  line-height: 1.4;
}

.presale__price:after {
  content: '预售价';
  width: 44px;
  height: 18px;
  font-size: 12px;
  font-family: PingFangSC-Regular, PingFangSC, 'sans-serif', 'SimHei', 'Noto Sans SC';
  font-weight: 400;
  border-radius: 4px;
  border: 1px solid rgba(255, 255, 255, 1);
  margin-left: 10px;
  text-align: center;
  display: inline-block;
  vertical-align: 5px;
  line-height: 16px;
  box-sizing: border-box;
}
.step__price {
  font-size: 14px;
  display: flex;
  align-items: center;
  margin-top: -7px;
  font-family: PingFangSC-Regular, PingFangSC, 'sans-serif', 'SimHei', 'Noto Sans SC';
  line-height: 1.4;
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
  font-family: PingFangSC-Semibold, PingFangSC, sans-serif;
  font-weight: 600;
  line-height: 1;
}

.m55__soldout-img,
.m55__remain-img {
  position: absolute;
  top: 50%;
  left: 50%;
  margin: -14.67vw 0 0 -14.67vw;
  width: 29.33vw;
  height: 29.33vw;
  z-index: 2;
}

.m55__wrapper--3 .m55__soldout-img,
.m55__wrapper--3 .m55__remain-img {
  margin: -10.67vw 0 0 -10.67vw;
  width: 21.33vw;
  height: 21.33vw;
}
</style>

<style>
.rebate-arr {
  margin-left: 4px;
  background-image: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACYAAAAnCAMAAABUv8o5AAAApVBMVEUAAAD/YGD/bGz/amr/Z2f/Zmb/amr/Y2P/ZGT/aWn+Z2f6VVX6VVX6VVX5VVX6Vlb6WVn/X1/6VVX5VVX6VVX6VVX6VVX6VVX7V1f6Vlb8W1v7WFj6VVX7WFj5WFj6V1f/ZWX/Zmb5VVX////7mZn5V1f+9vb7qan7oKD6jIz6g4P6c3P+6+v94+P92tr9z8/8w8P8t7f5Zmb5YWH5XFz+8fH5aGgrtBT2AAAAInRSTlMAAwcSChcPDCAcJvvp8OKYXhP13Mu8pp2DZ1eRkIaGbSsj7H3HGQAAAY1JREFUOMu10tlygkAQBdAwwzIsCqgg4N6oUbNptv//tLQDsyHmIVW5z6f6Nj08/GMsDElTYmF+QWmZj0OAcJyXKcJ+xOIRyIxi1gOxbDUAI4MVlneVN4WbTD10psqgJxk6ozGG3sR6r0VKuJOSWEoxuf3ucNgZ38HQCTYHkW1dv33qbi4Y3l2d4ljX9euHPi5tnWUnoPKI7uUbVBLbaoaZJ9uie37Sj0csztwJ6Dnu6/pLuYkrWARGTuj20kUts2kohdrvAG1CardsJIHa7l3+Kg0jHpWl6lulgoh6pGHGJ1w6l5sga0q1d9+d6847xHK3ytzrbLxq1TLi+pH+WBfQE/nibp6z1I52AiNLxxOMBkO4k2FAOeOtThL2qzBxeGc7zl/0s4XfDBPjWN6ncsaHCWajK8KbxgKVjUw56rBk2Nk+YQ4VSqyHbl0MNVSsUfHFFOO9PguqWTaOonE2qwLm80bBlKMINwHPBhFVSu/l0PF5HI5Eo+Gu0HMpj+tdkVJdiBRDiET9UubhL/kBQUtjQIXKX6IAAAAASUVORK5CYII=');
}
</style>

<template>
  <div class="m55 cfix">
    <!-- <infinite-panel :show-spinner="false" :busy="loadingItem" :is-end="isEnd" @loadmore="loadMoreItems"> -->
    <template v-for="item in itemList">
      <navigator :url="item.goalUri || item.url" class="m55__wrapper" :class="'m55__wrapper--' + tplData.column" :self-data="item.selfData" data-emergence="hidden" prefix="m55">
        <div class="m55__img" :style="{ backgroundImage: 'url(' + getImgHeadPic(item) + ')' }">
          <template v-if="item.soldOut">
            <img src="https://pic.wanwustore.cn/Fp01CrHd8u_xRY-wY8e0_bFJWJXW" class="m55__soldout-img" />
          </template>
          <template v-else>
            <img v-if="item.itemStatus && item.itemStatus === 'ready'" src="https://pic.wanwustore.cn/FumoB7hgF5Nda_yt7byUbK6w7Bs-" class="m55__remain-img" />
          </template>

          <div v-if="tplData.column > 1 && item.extra.tag" class="m55__tag">{{ item.extra.tag }}</div>
          <div v-if="item.extra.saleNum" class="m55__salenum line line-1">热销{{ item.extra.saleNum }}件</div>
          <!-- 到手价 -->
          <div class="hand-panel" v-if="item.handPriceBanner && tplData.column == 2" :class="{ btom100: item.presale }">
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
          <template v-if="item.presale && tplData.column == 2">
            <div class="presale-panel">
              <p class="presale__price">{{ item.presale.sellPrice }}</p>
              <div class="step__price">
                <p class="front__price">定金 {{ item.presale.frontPrice }}</p>
                <p class="front__price">尾款 {{ item.presale.endPrice }}</p>
              </div>
            </div>
          </template>
        </div>
        <div class="m55__item">
          <div class="m55__name line line-2">{{ item.name }}</div>
          <div v-if="tplData.column == 1" class="m55__tag__wrapper">
            <div v-if="item.extra.tag" class="m55__tag">{{ item.extra.tag }}</div>
          </div>
          <div class="m55__price">
            <div class="m55__sellprice">￥{{ item.predictPrice ? item.predictPrice : item.sellPrice }}</div>
            <div v-if="item.predictPrice ? item.predictPrice !== item.originPrice : item.sellPrice !== item.originPrice" class="m55__originprice">￥{{ item.originPrice }}</div>
          </div>
          <div class="m55__btn">
            <div v-if="item.rebate" class="m55__rabate">返{{ item.rebate }}<icon type="rebate-arr" :width="38"> </icon></div>
            <div v-else class="m55__view"></div>
          </div>
        </div>
      </navigator>
    </template>
    <!-- </infinite-panel> -->
  </div>
</template>

<script>
//TODO
// import API from 'api/api'
export default {
  data() {
    return {
      loadingItem: false
    }
  },
  props: {
    tplData: {
      type: Object,
      default: () => {}
    },
    activityId: {
      type: String,
      default: ''
    }
  },
  computed: {
    // onePage() {
    //   return this.tplData.count < 0
    // },
    itemList() {
      if (!this.needCountly) return this.tplData.itemList
      this.tplData.itemList.forEach((item, index) => {
        let obj = {
          eleType: 'item',
          activityTpl: 'm55',
          connid: this.tplData.connId,
          itemId: item.itemId,
          logId: item.logId,
          activityId: this.activityId,
          index
        }
        if (item.predictPrice) {
          obj.predictPrice = item.predictPrice
        }
        let selfData = JSON.stringify(obj)
        this.$set(this.tplData.itemList[index], 'selfData', selfData)
        // let presale = {
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
        // let handPriceBanner = {
        //   handPriceTag: '最终到手价',
        //   handPrice: '999.9',
        //   formula: '到手价=售价￥169-活动优惠￥20-优惠券￥10-分润(双倍)￥5x2',
        //   handPriceNotice: 'TIME:11.1 00:00-11.12 24:00'
        // }
        // this.$set(this.tplData.itemList[index], 'presale', presale)
        // this.$set(this.tplData.itemList[index], 'handPriceBanner', handPriceBanner)
      })
      return this.tplData.itemList
    },
    isEnd() {
      return this.tplData.isEnd
    },
    boundaryId() {
      return this.tplData.startId
    },
    param() {
      var param = {
        mode: 'getItemList',
        actid: this.$parent.activityInfo.id,
        connid: this.tplData.connId
      }
      param['data[startId]'] = this.boundaryId
      return param
    }
  },
  methods: {
    getImgHeadPic(item) {
      return item.extra.headPic || item.picUrl
    },
    async loadMoreItems() {
      if (this.loadingItem) return
      this.loadingItem = true
      try {
        let res = await this.request.get(API.actgetdata, { params: this.param })
        console.log(res.data.data)
        if (res.data.errno == 0) {
          let _data = res.data.data
          this.tplData.isEnd = _data.isEnd
          this.tplData.itemList = this.tplData.itemList.concat(_data.itemList)
          this.tplData.startId = _data.startId
        } else {
          this.count++
          if (this.count >= 3) {
            this.tplData.isEnd = true
          }
        }
      } catch (e) {
        // alert('网络错误')
        console.log('网络错误')
        console.log(e)
      } finally {
        this.loadingItem = false
      }
    }
  },
  components: {
    // API
  },
  mounted() {}
}
</script>
