<style>
.swiper-slide {
  height: 100%;
}

.m44-swiper-container {
  position: relative;
  width: 100%;
  overflow: hidden;
}

.m44-slide-img {
  display: block;
  margin: 0 auto;
}

.m44-swiper-pagination {
  position: absolute;
  z-index: 20;
  bottom: 10px;
  width: 100%;
  text-align: center;
}

.m44-bullet-active {
  opacity: 1 !important;
  background-color: #000 !important;
}

.m44-bullet {
  width: 16px;
  height: 16px;
  display: inline-block;
  border-radius: 100%;
  margin-left: 10px;
  background-color: #aaa;
}

.m44__link {
  display: block;
  border: 10px solid gold;
  box-sizing: border-box;
}
</style>

<template>
  <div :id="'s' + tplData.connId" class="m44-swiper-container" :style="{ height: height }">
    <div class="swiper-wrapper" @click="bannerLink">
      <div class="swiper-slide" v-for="(banner, index) in bannerList" :key="index" :class="{ 'swiper-no-swiping': bannerList.length === 1 }">
        <img class="m44-slide-img" :style="{ height: height }" :src="banner.pic" alt="" />
      </div>
    </div>
    <div v-if="bannerList.length > 1" class="m44-swiper-pagination"></div>
  </div>
</template>

<script>
// import 'swiper/dist/css/swiper.min.css'
// import Swiper from 'swiper'

export default {
  data() {
    return {
      swiper: null
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
    bannerList() {
      if (!this.tplData || !this.tplData.bannerList) return []
      return this.tplData.bannerList
    },
    height() {
      if (!this.tplData || !this.tplData.bannerList) return 0
      let _h = this.tplData.bannerList[0].height
      let _w = 750
      return (_h * document.body.clientWidth) / _w + 'px'
    }
  },
  methods: {
    bannerLink() {
      if (!this.bannerList || !this.swiper) return
      let url = this.bannerList[this.swiper.realIndex]['url']
      this.navTo(url)
    }
  },
  mounted() {
    let loop = true
    let autoplay = {
      delay: 3000,
      disableOnInteraction: false
    }
    if (this.tplData.bannerList.length < 2) {
      ;(loop = false), (autoplay = false)
    }
    this.swiper = new Swiper(`#s${this.tplData.connId}`, {
      loop,
      autoplay,
      freeMode: false,
      pagination: {
        el: '.m44-swiper-pagination',
        bulletClass: 'm44-bullet',
        bulletActiveClass: 'm44-bullet-active'
      }
    })
  }
}
</script>
