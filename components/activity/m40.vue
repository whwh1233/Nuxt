<style>
.m40 {
  overflow: hidden;
}

.m40__container {
  white-space: nowrap;
  box-sizing: content-box;
  overflow-x: auto;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
  font-size: 0;
}

.m40__item {
  display: inline-block;
  height: 100%;
}

.m40__img {
  display: block;
  width: 100%;
  height: 100%;
}
</style>

<template>
  <div class="m40" :style="{ height: height }" :data-sort="tplData.sort">
    <div :id="'m40__container__' + tplData.connId" class="m40__container" :style="{ height: height }">
      <navigator
        class="m40__item"
        v-for="(banner, bannerIndex) in bannerList"
        :url="banner.url"
        :key="bannerIndex"
        :style="{ width: banner.width ? banner.width + 'px' : '' }"
        :self-data="banner.selfData"
        data-emergence="hidden"
        prefix="m40"
      >
        <img class="m40__img" :src="banner.pic" />
      </navigator>
    </div>
  </div>
</template>

<script>
export default {
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
      return this.tplData.bannerList.map((banner, index) => {
        let obj = {
          eleType: 'swiper',
          activityTpl: 'm40',
          connid: this.tplData.connId,
          img: banner.pic,
          url: banner.url,
          logId: banner.logId,
          index
        }
        banner.selfData = JSON.stringify(obj)
        return banner
      })
    },
    height() {
      return this.tplData.bannerList[0].height + 'px'
    }
  },
  mounted() {
    this.$nextTick(() => {
      let container = document.getElementById('m40__container__' + this.tplData.connId)
      let em = (this.$root.$children && this.$root.$children[0] && this.$root.$children[0].em) || null
      let poll
      if (em) {
        container.addEventListener('scroll', () => {
          if (!!poll) {
            return
          }
          clearTimeout(poll)
          poll = setTimeout(() => {
            em.engage()
            poll = null
          }, 1000)
        })
      }
    })
  }
}
</script>
