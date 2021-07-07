<style>
/*.m59 .sticky {
    width: 100%;
  }*/

.m59__nav__wrapper {
  width: 100%;
  overflow-x: auto;
}

.m59__nav {
  padding-left: 40px;
  height: 158px;
  /*border-bottom: 1px solid #EEE;*/
  /* background: #fff; */
  white-space: nowrap;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
}

.m59__nav__el {
  position: relative;
  display: inline-block;
  vertical-align: middle;
  margin-right: 70px;
  height: 158px;
  text-align: center;
}

.m59__nav__el--active:after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: 30px;
  transform: translateX(-50%);
  width: 32px;
  height: 10px;
  background: linear-gradient(180deg, rgba(253, 85, 100, 1) 0%, rgba(252, 89, 77, 1) 100%);
  opacity: 1;
  border-radius: 5px;
}

.m59__nav__el__primary {
  margin-top: 39px;
  width: 100%;
  font-size: 30px;
  font-family: PingFang SC;
  font-weight: bolder;
}

.m59__nav__el__desc {
  position: absolute;
  top: 76px;
  width: 100%;
  font-size: 20px;
}

.m59__nav__el--active .m59__nav__el__primary {
  margin-top: 30px;
  font-size: 38px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
}

.m59__nav__el--active .m59__nav__el__desc {
  font-size: 24px;
}

.m59__loading {
  width: 100%;
  height: 500px;
  background-image: url('https://pic.wanwustore.cn/FmE4EicjK_zK47ItEPK8MrTXaDAo');
  background-repeat: no-repeat;
  background-position: center;
  background-size: 66px;
}
.m59__content {
  min-height: 100px;
}
.m59__fix {
  position: sticky;
  top: 0px;
  z-index: 10000;
}
.isline1 .m59__nav,
.isline1 .m59__nav__el {
  height: 120px;
}
.isline1 .m59__nav__el--active:after {
  bottom: 20px;
}

.m59__act-limited {
  height: 400px;
  overflow: auto;
}
</style>

<template>
  <div class="m59" :class="{ isline1: !isLine2 }">
    <!-- <sticky top="0"> -->
    <div>
      {{ tplData }}
    </div>
    <div class="m59__nav__wrapper" :class="navFixed ? 'm59__fix' : ''">
      <div class="m59__nav" :style="{ backgroundColor: bgColor }">
        <div
          v-for="(nav, i) in tplData.rushInfo"
          :key="i"
          class="m59__nav__el"
          :class="{ 'm59__nav__el--active': current === nav.id }"
          @click="changeTab(nav)"
          :style="{ color: current === nav.id ? activeTextColor : textColor }"
        >
          <p class="m59__nav__el__primary">{{ nav.primary }}</p>
          <p class="m59__nav__el__desc">{{ nav.desc }}</p>
        </div>
      </div>
    </div>
    <!-- </sticky> -->

    <div class="m59__content">
      <div class="m59__act-limited">
        <act-panel :id="tplData.rushInfo[1].id"></act-panel>
      </div>
      <!-- <template v-for="obj in tplData.rushInfo">
        <div v-show="current === obj.id" class="m59__content__el">
          <div class="m59__loading" v-show="!obj.loaded"></div>
          <template v-if="obj.visited">
            <div v-show="obj.loaded">
              <act-panel @actpanel-loaded="actLoaded" :id="obj.id"></act-panel>
            </div>
          </template>
        </div>
      </template> -->
    </div>
  </div>
</template>

<script>
// import sticky from 'vue-sticky-position'

export default {
  data() {
    return {
      $nav: null,
      _w: 0,
      nowId: 0,
      firstLoaded: false
    }
  },
  computed: {
    firstEl() {
      if (!this.tplData || !this.tplData.rushInfo) return null
      return this.tplData.rushInfo[0]
    },
    textColor() {
      if (!this.firstEl) return '#AAA'
      return this.firstEl.textColor || '#AAA'
    },
    activeTextColor() {
      if (!this.firstEl) return '#000'
      return this.firstEl.activeTextColor || '#000'
    },
    bgColor() {
      if (!this.firstEl) return '#FFF'
      return this.firstEl.bgColor || '#FFF'
    },
    navFixed() {
      return this.tplData.fixTop === 'on'
    },
    //是否展示两行数据
    isLine2() {
      return this.tplData.rushInfo.some(nav => {
        return nav.desc !== ''
      })
    },
    current() {
      if (this.nowId) {
        return this.nowId
      }
      let arr = this.tplData.rushInfo.filter(info => info.active) || this.tplData.rushInfo[0]
      return arr[0]['id']
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
  components: {
    // actPanel
    // sticky
  },
  methods: {
    changeTab(nav) {
      if (!nav.id) return
      this.nowId = nav.id
      nav.visited = true
      let scrollTop = document.querySelector('.m59').offsetTop - document.body.scrollTop
      console.log(document.querySelector('.m59').offsetTop)
      console.log(document.body.scrollTop)
      if (scrollTop < 0) {
        window.scrollBy(0, scrollTop)
      }
      this.$nextTick(() => {
        this.scrollToView()
      })
    },
    scrollToView(smoothly = true) {
      this.$nav = this.$nav || document.querySelector('.m59__nav')
      this._w = this._w || this.$nav.getBoundingClientRect().width
      let $current = document.querySelector('.m59__nav__el--active')
      let rect = $current.getBoundingClientRect()
      let _xl = rect.left
      let _xr = _xl + rect.width

      if (_xr > this._w - 200 || _xl < 0) {
        if (!smoothly) {
          this.$nav.scrollLeft = _xl
        } else {
          this.scrollSmoothly(_xl)
        }
      }
    },
    scrollSmoothly(diff) {
      let one = (diff / 5) | 0
      let i = 0
      let timer = setInterval(() => {
        if (++i >= 5) {
          clearInterval(timer)
          timer = 0
        }
        this.$nav.scrollLeft += one
      }, 30)
    },
    actLoaded({ id }) {
      this.tplData.rushInfo = this.tplData.rushInfo.map(one => {
        if (one.id === id) {
          one.loaded = true
        }
        return one
      })
      if (!this.firstLoaded) {
        this.firstLoaded = true
        this.$emit('load', this.tplData.connId)
      }
    }
  },
  mounted() {
    this.scrollToView(false)

    this.tplData.rushInfo = this.tplData.rushInfo.map(info => {
      info.visited = this.current === info.id
      info.loaded = false
      return info
    })
  }
}
</script>
