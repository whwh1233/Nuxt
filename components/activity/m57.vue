<style>
.m57__wrapper {
  font-size: 0;
}

.m57__el {
  display: inline-block;
}

.m57__img {
  display: block;
  width: 100%;
  height: 100%;
}
</style>

<template>
  <div>
    <!-- TODO
    去除  v-if="bannerList.length" -->
    <template>
      <section class="m57__wrapper" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
        <navigator v-for="(banner, index) in bannerList" :key="index" :url="banner.url" class="m57__el" :style="{ width: banner.width, height: banner.height }">
          <img class="m57__img" :src="banner.bgimg" />
        </navigator>
      </section>
    </template>
    <!-- TODO -->
    <!-- 去除v-else -->
    <template>
      <section class="banner__row" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
        <navigator v-for="(banner, index) in tplData.bannerList" :key="index" :url="banner.url" class="banner__el">
          <img class="banner__img" :src="banner.bgimg" />
        </navigator>
      </section>
    </template>
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
      if (process.browser) {
        if (!this.tplData || !this.tplData.bannerList) return []
        if (!this.tplData.ratio) return []
        let bannerList = this.tplData.bannerList
        if (!bannerList.length) return []
        let n = bannerList.length
        let lastN = n - 1
        let firstOne = bannerList[0]
        if (!firstOne) return []
        let parentWidth = 10000
        if (this.$parent && this.$parent.$el && this.$parent.$el.clientWidth) {
          parentWidth = this.$parent.$el.clientWidth
          // console.log(parentWidth)
        }
        let screenWidth = Math.min(document.body.clientWidth, window.screen.width * 2, parentWidth)
        let w = screenWidth / n
        w = ((w / 2) | 0) * 2
        let h = screenWidth / (bannerList.length * +this.tplData.ratio)
        h = ((h / 2) | 0) * 2
        return bannerList.map((banner, i) => {
          banner.height = h + 'px'
          let width = i >= lastN ? screenWidth - lastN * w : w
          banner.width = width + 'px'
          return banner
        })
      }
    }
  }
}
</script>
