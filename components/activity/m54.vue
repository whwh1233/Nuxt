<style>
.m54 .sticky {
  width: 100%;
}

.m54__nav__wrapper {
  width: 100%;
  overflow-x: auto;
}

.m54__nav {
  padding-left: 26px;
  height: 70px;
  border-bottom: 1px solid #eee;
  background: #fff;
  white-space: nowrap;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
}

.m54__nav__el {
  position: relative;
  display: inline-block;
  vertical-align: middle;
  margin-right: 30px;
  padding: 14px 10px 0;
  height: 70px;
  text-align: center;
}

.m54__nav__el--active {
  color: #f95555;
}

.m54__nav__el--active:after {
  content: '';
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 6px;
  background: #f95555;
}

.m54__nav__el__primary {
  width: 100%;
  font-size: 28px;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}

.m54__loading {
  width: 100%;
  height: 500px;
  background-image: url('https://pic.wanwustore.cn/FmE4EicjK_zK47ItEPK8MrTXaDAo');
  background-repeat: no-repeat;
  background-position: center;
  background-size: 66px;
}
.m54__content {
  min-height: 100px;
}
</style>

<template>
  <div class="m54">
    <sticky top="0">
      <div class="m54__nav__wrapper">
        <div class="m54__nav">
          <div v-for="(nav, index) in tplData.tabInfo" :key="index" class="m54__nav__el" :class="{ 'm54__nav__el--active': current === nav.id }" @click="changeTab(nav)">
            <p class="m54__nav__el__primary">{{ nav.label }}</p>
          </div>
        </div>
      </div>
    </sticky>

    <div class="m54__content">
      <template v-for="obj in tplData.tabInfo">
        <div v-show="current === obj.id" class="m54__content__el">
          <div class="m54__loading" v-show="!obj.loaded"></div>
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
// import actPanel from './act-panel'
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
      let first = this.tplData.tabInfo[0]
      return first && first['id']
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
    // actPanel,
    // sticky
  },
  methods: {
    changeTab(nav) {
      if (!nav.id) return
      this.nowId = nav.id
      nav.visited = true
      let scrollTop = document.querySelector('.m54').offsetTop - document.body.scrollTop
      if (scrollTop < 0) {
        window.scrollBy(0, scrollTop)
      }
      this.$nextTick(() => {
        this.scrollToView()
      })
    },
    scrollToView(smoothly = true) {
      this.$nav = this.$nav || document.querySelector('.m54__nav')
      this._w = this._w || this.$nav.getBoundingClientRect().width
      let $current = document.querySelector('.m54__nav__el--active')
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
      this.tplData.tabInfo = this.tplData.tabInfo.map(one => {
        if (one.id === id) {
          one.loaded = true
        }
        return one
      })
    }
  },
  mounted() {
    this.scrollToView(false)

    this.tplData.tabInfo = this.tplData.tabInfo.map(info => {
      info.visited = this.current === info.id
      info.loaded = false
      return info
    })
  }
}
</script>
