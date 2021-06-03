<style>
/*.m52 .sticky {
    width: 100%;
  }*/

.m52__nav__wrapper {
  width: 100%;
  overflow-x: auto;
}

.m52__nav {
  padding-left: 16px;
  height: 140px;
  border-bottom: 1px solid #eee;
  background: #fff;
  white-space: nowrap;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
}

.m52__nav__el {
  position: relative;
  display: inline-block;
  vertical-align: middle;
  margin-right: 20px;
  width: 150px;
  height: 140px;
  text-align: center;
}

.m52__nav__el--active {
  color: #f95555;
}

.m52__nav__el--active:after {
  content: '';
  position: absolute;
  left: 50%;
  bottom: 20px;
  width: 86px;
  height: 8px;
  background: #f95555;
  transform: translateX(-50%);
}

.m52__nav__el__primary {
  position: absolute;
  top: 30px;
  width: 100%;
  font-size: 30px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}

.m52__nav__el__desc {
  position: absolute;
  top: 68px;
  width: 100%;
  font-size: 26px;
}

.m52__nav__el--active .m52__nav__el__primary {
  top: 27px;
  font-size: 32px;
}

.m52__nav__el--active .m52__nav__el__desc {
  font-size: 28px;
}

.m52__loading {
  width: 100%;
  height: 500px;
  background-image: url('https://pic.wanwustore.cn/FmE4EicjK_zK47ItEPK8MrTXaDAo');
  background-repeat: no-repeat;
  background-position: center;
  background-size: 66px;
}
.m52__content {
  min-height: 100px;
}
</style>

<template>
  <div class="m52">
    <!-- <sticky top="0"> -->
    <div class="m52__nav__wrapper">
      <div class="m52__nav">
        <div v-for="(nav, index) in tplData.rushInfo" :key="index" class="m52__nav__el" :class="{ 'm52__nav__el--active': current === nav.id }" @click="changeTab(nav)">
          <p class="m52__nav__el__primary">{{ nav.primary }}</p>
          <p class="m52__nav__el__desc">{{ nav.desc }}</p>
        </div>
      </div>
    </div>
    <!-- </sticky> -->

    <div class="m52__content">
      <template v-for="obj in tplData.rushInfo">
        <div v-show="current === obj.id" class="m52__content__el">
          <div class="m52__loading" v-show="!obj.loaded"></div>
          <template v-if="obj.visited">
            <div v-show="obj.loaded">
              <act-panel @actpanel-loaded="actLoaded" :id="obj.id"></act-panel>
            </div>
          </template>
        </div>
      </template>
    </div>
  </div>
</template>

<script>
import actPanel from './act-panel'
// import sticky from 'vue-sticky-position'

export default {
  data() {
    return {
      $nav: null,
      _w: 0,
      nowId: 0
    }
  },
  computed: {
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
    actPanel
    // sticky
  },
  methods: {
    changeTab(nav) {
      if (!nav.id) return
      this.nowId = nav.id
      nav.visited = true
      let scrollTop = document.querySelector('.m52').offsetTop - document.body.scrollTop
      if (scrollTop < 0) {
        window.scrollBy(0, scrollTop)
      }
      this.$nextTick(() => {
        this.scrollToView()
      })
    },
    scrollToView(smoothly = true) {
      this.$nav = this.$nav || document.querySelector('.m52__nav')
      this._w = this._w || this.$nav.getBoundingClientRect().width
      let $current = document.querySelector('.m52__nav__el--active')
      let rect = $current.getBoundingClientRect()
      let _xl = rect.left
      let _xr = _xl + rect.width
      if (_xr > this._w || _xl < 0) {
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
