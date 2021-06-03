<style>
.swiper-wrapper {
  width: 100%;
}
.swiper-slide {
  height: 100%;
  font-size: 0px;
}
.swiper-wrapper-box {
  position: relative;
  margin: 0 auto;
  border-radius: 50px !important;
  z-index: 100;
  overflow: hidden !important;
}
.m56-swiper-container {
  position: relative;
  padding: 16px 0px 10px;
  width: 100%;
  box-sizing: border-box;
  background-size: cover;
  overflow: auto;
}
.m56-slide-img {
  display: block;
  width: 100%;
  height: 100%;
}
.m56-swiper-pagination {
  position: absolute;
  bottom: 9px !important;
  width: 100%;
  text-align: center;
  z-index: 20;
}
.m56-bullet-active {
  opacity: 1 !important;
  background: linear-gradient(90deg, rgba(247, 79, 66, 1) 0%, rgba(224, 66, 55, 1) 100%) !important;
}
.m56-bullet {
  display: inline-block;
  margin-left: 20px;
  width: 16px;
  height: 16px;
  border-radius: 50%;
  opacity: 0.5;
  background-color: #fff;
}

.m56__link {
  display: block;
  border: 10px solid gold;
  box-sizing: border-box;
}
</style>

<template>
  <div class="m56-swiper-container" :style="{ backgroundImage: 'url(' + tplData.bgImg + ')' }">
    <div class="swiper-wrapper-box" :id="'s' + tplData.connId" :style="{ width: width, height: height }" :self-data="selfData" data-emergence="hidden" prefix="m56">
      <div class="swiper-wrapper">
        <div class="swiper-slide" v-for="(banner, index) in bannerList" :key="index">
          <navigator :url="banner.url" :self-data="selfData" prefix="m56" type="swiper">
            <img class="m56-slide-img" :src="banner.pic" alt="" />
          </navigator>
        </div>
      </div>
      <div class="m56-swiper-pagination"></div>
    </div>
  </div>
</template>

<script>
// import 'swiper/dist/css/swiper.min.css'
// import Swiper from 'swiper'

export default {
  data() {
    return {
      swiper: null,
      selfData: '',
      moveBusy: false
    }
  },
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    },
    activityId: {
      type: String,
      default: ''
    }
  },
  computed: {
    bannerList() {
      if (!this.tplData || !this.tplData.bannerList) return []
      return this.tplData.bannerList
    },
    height() {
      if (!this.tplData || !this.tplData.bannerList) return 0
      let _h = this.tplData.bannerList[0].height
      let h = (_h * document.body.clientWidth) / 750
      return ((h / 2) | 0) * 2 + 'px'
    },
    width() {
      if (!this.tplData || !this.tplData.bannerList) return 0
      let w = (710 / 750) * document.body.clientWidth
      return ((w / 2) | 0) * 2 + 'px'
    }
  },
  methods: {},
  mounted() {
    let loopFlag = this.tplData.bannerList.length > 1 ? true : false
    this.$nextTick(() => {
      this.swiper = new Swiper(`#s${this.tplData.connId}`, {
        loop: false,
        autoplay: {
          delay: 3000,
          disableOnInteraction: false
        },
        freeMode: false,
        pagination: {
          el: '.m56-swiper-pagination',
          bulletClass: 'm56-bullet',
          bulletActiveClass: 'm56-bullet-active'
        },
        on: {
          slideChangeTransitionEnd: () => {
            if (!this.needCountly) return
            if (this.swiper) {
              let index = this.swiper.realIndex
              let selfDataObj = {
                // page: 'home',
                eleType: 'swiper',
                activityTpl: 'm56',
                connid: this.tplData.connId,
                img: this.bannerList[index].pic,
                url: this.bannerList[index].url,
                logId: this.bannerList[index].logId,
                activityId: this.activityId,
                index
              }
              this.selfData = JSON.stringify(selfDataObj)
              document.querySelector(`#s${this.tplData.connId}`).setAttribute('self-data', this.selfData)
            }
          },
          touchMove: () => {
            if (!this.needCountly) return
            if (!this.moveBusy) {
              this.moveBusy = true
              setTimeout(() => {
                let selfData = document.querySelector(`#s${this.tplData.connId}`).getAttribute('self-data')
                let prefix = document.querySelector(`#s${this.tplData.connId}`).getAttribute('prefix')
                this.saveCountlyData({ selfData, prefix }, 'countlyScrollData')
                this.moveBusy = false
              }, 500)
            }
          }
        }
      })
      if (!this.needCountly) return
      let index = 0
      let obj = {
        // page: 'home',
        eleType: 'swiper',
        activityTpl: 'm56',
        connid: this.tplData.connId,
        img: this.bannerList[index].pic,
        url: this.bannerList[index].url,
        index
      }
      this.selfData = JSON.stringify(obj)
      document.querySelector(`#s${this.tplData.connId}`).setAttribute('self-data', this.selfData)
    })
  }
}
</script>
