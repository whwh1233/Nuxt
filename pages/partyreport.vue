<style scoped>
* {
  margin: 0;
  padding: 0;
}
.main {
  margin: 0 auto;
  position: relative;
  width: 750px;
  height: 1000px;
  overflow: hidden;
  background: rgba(0, 0, 0, 0.24) linear-gradient(180deg, rgba(0, 0, 0, 0.64) 0%, rgba(0, 0, 0, 0.48) 50%, rgba(0, 0, 0, 0) 100%);
  background: no-repeat;
  background-size: cover;
}
.main__onemart {
  position: absolute;
  width: 200px;
  height: 104px;
  background: url('https://pic.bbtkids.cn/Fhml8D0BQGDP1OpxTrUnM7QJBEya');
  background-size: contain;
}

.main__text__content {
  margin-top: 50px;
  margin-left: 42px;
  height: 144px;
  width: 508px;
  font-size: 64px;
  /* font-family: Alibaba-PuHuiTi-H, Alibaba-PuHuiTi; */
  font-family: bbt-Regular, PingFang SC;
  font-weight: normal;
  color: #ffffff;
  line-height: 64px;
  letter-spacing: 1px;
}
.main__text__img {
  position: absolute;
  right: -32px;
  top: 48px;
  width: 140px;
  height: 140px;
  background: url('https://pic.bbtkids.cn/FjLS36IbcVmYXXBz6mqddkBaXPlT') no-repeat;
  background-size: contain;
}

.main__info__owner {
  margin-top: 28px;
  margin-left: 40px;
  margin-bottom: 28px;
  display: flex;
  align-items: center;
  font-size: 26px;
  line-height: 37px;
  color: #fff;
  text-shadow: 0px 1px 6px rgba(0, 0, 0, 0.64);
}

.main__info__owner__img {
  margin-right: 12px;
  width: 64px;
  height: 64px;
  background-size: contain;
  border-radius: 64px;
}

.main__info__other__el {
  margin-top: 20px;
  margin-left: 46px;
  display: flex;
  align-items: center;
  font-size: 26px;
  line-height: 37px;
  color: #fff;
  text-shadow: 0px 1px 6px rgba(0, 0, 0, 0.64);
}

.main__info__other__el__img {
  margin-right: 8px;
  width: 32px;
  height: 32px;
  background-size: contain;
}

.main__party {
  position: absolute;
  bottom: 8px;
  right: 8px;
  width: 114px;
  height: 146px;
  background: #0c0c0c;
  border-radius: 14px;
}

.img__group {
  margin-top: 9px;
  padding-bottom: 9px;
  border-bottom: 1px solid #fff;
}

.main__party__img {
  margin-top: 0;
  margin-left: 9px;
  margin-right: 9px;
  width: 96px;
  height: 96px;
  background: url('https://pic.bbtkids.cn/FoeEBEZdeOThKRiXxNXpITbQVxWm');
  background-size: contain;
  box-shadow: 0px 1px 0px 0px rgba(255, 255, 255, 0.36);
}

.main__party__text {
  margin-top: 5px;
  font-size: 15px;
  text-align: center;
  color: #1effb2;
}
</style>

<template>
  <div>
    <div class="main" :style="{ backgroundImage: 'url(' + picUrl + ')' }">
      <div class="main__onemart"></div>
      <div class="main__text__content">{{ topic }}</div>

      <div class="main__text__img"></div>
      <div class="main__info">
        <div class="main__info__owner">
          <img :src="faceUrl" class="main__info__owner__img" />
          主理人：{{ nick }}
        </div>
        <div class="main__info__other">
          <div class="main__info__other__el">
            <img src="https://pic.bbtkids.cn/FiJvEwUiDdsQP2ZlHeHJy95ChV4u" class="main__info__other__el__img" />

            日期：8月2日
          </div>
          <div class="main__info__other__el">
            <img src="https://pic.bbtkids.cn/FjcNpQWNevlvb_WcVOjGUGwIou1g" class="main__info__other__el__img" />

            时间：下午5:00
          </div>
        </div>
      </div>
      <div class="main__party">
        <div class="img__group">
          <div class="main__party__img"></div>
        </div>
        <div class="main__party__text">扫码参加派对</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    const res = await $axios.$post('http://apidev.bangbangtown.cn/1.0/uiforum/wapqrcpage?auctionId=1000130&pageName=auction')
    let pageData = res.data.pageData

    // console.log(pageData)
    return {
      auction: pageData.auction,
      topic: pageData.auction.topic || '',
      picUrl: pageData.auction.picUrl || '',
      faceUrl: pageData.auction.user.faceUrl || '',
      nick: pageData.auction.user.nick || '',
      date: '',
      time: ''
    }
  },

  data() {
    return {
      // auction: pageData.auction,
      // topic: pageData.auction.topic || '',
      // picUrl: pageData.auction.picUrl || '',
      // faceUrl: pageData.auction.user.faceUrl || '',
      // nick: pageData.auction.user.nick || '',
      // date: '',
      // time: ''
      topic: 'no message'
    }
  }
}
</script>
