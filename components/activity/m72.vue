<style scoped>
.m72__wrapper {
  position: fixed;
  bottom: 6%;
  right: -27vh;
  width: 27vh;
  height: 90vh;
  /* padding-bottom: 166.67%; */
  transition: transform 0.3s ease;
  z-index: 100000;
}
.m72__wrapper--active {
  width: 27vh;
  height: 90vh;
  /* padding-bottom: 166.67%; */
  transform: translate(-100%, 0);
}
.m72__panel {
  display: flex;
  align-items: center;
  position: absolute;
  left: 0;
  top: 0;
  right: 0;
  bottom: 0;
  margin: auto;
}
.m72__imgbox {
  position: relative;
  width: 100%;
}
.m72__arrow {
  position: absolute;
  top: 50%;
  transform: translate(-100%, -50%);
  background: no-repeat center/contain;
}
.m72__arrow--fold {
  width: 7vh;
  height: 21vh;
}
.m72__arrow--unfold {
  width: 60px;
  height: 70px;
}
.modal {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.7);
  z-index: 10000;
}
</style>

<template>
  <div>
    <div v-show="!hideFixedButton" class="m72__wrapper" :class="{ 'm72__wrapper--active': showSideBar }">
      <div class="m72__panel">
        <div class="m72__imgbox">
          <div class="m72__arrow" :class="showSideBar ? 'm72__arrow--unfold' : 'm72__arrow--fold'" @click="toggle" :style="{ backgroundImage: 'url(' + arrowBg + ')' }"></div>
          <navigator v-for="(banner, bannerIndex) in tplData.bannerList" :url="banner.url" :key="bannerIndex" class="banner__el">
            <img class="banner__img" :src="banner.bgimg" />
          </navigator>
        </div>
      </div>
    </div>
    <div class="modal" @click.stop="toggle" v-show="showSideBar"></div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showSideBar: false
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
    arrowBg() {
      if (!this.tplData) return ''
      return this.showSideBar ? this.tplData.unfoldPic : this.tplData.foldPic
    },
    hideFixedButton() {
      return this.$parent && this.$parent.hideFixedButton
    }
  },
  methods: {
    toggle() {
      this.showSideBar = !this.showSideBar
    }
  }
}
</script>
