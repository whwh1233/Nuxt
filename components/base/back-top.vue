<style>
.back-to-top-fade-enter-active,
.back-to-top-fade-leave-active {
  transition: opacity 0.7s;
}

.back-to-top-fade-enter,
.back-to-top-fade-leave-to {
  opacity: 0;
}

.back-to-top {
  position: fixed;
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background: rgba(0, 0, 0, 0.6) url('https://pic.bbtkids.cn/FoJ0yvPqsmfvARKfZuFEKNPEk5xC') no-repeat center/45% 45%;
  z-index: 200;
}
</style>

<template>
  <transition name="back-to-top-fade">
    <div class="back-to-top" :style="`bottom:${this.bottom}px;right:${this.right}px;`" v-show="showIt" @click="backToTop">
      <slot></slot>
    </div>
  </transition>
</template>

<script>
export default {
  data() {
    return {
      showIt: false
    }
  },
  props: {
    right: {
      type: Number,
      default: 40
    },
    bottom: {
      type: Number,
      default: 40
    }
  },
  methods: {
    catchScroll() {
      this.showIt = window.pageYOffset > 600
    },
    backToTop() {
      let currentScroll = document.documentElement.scrollTop || document.body.scrollTop
      if (currentScroll > 0) {
        window.requestAnimationFrame(this.backToTop)
        window.scrollTo(0, Math.floor(currentScroll - currentScroll / 5))
      }
    }
  },
  mounted() {
    console.log('backtop')
    window.addEventListener('scroll', this.catchScroll)
  },
  destroyed() {
    window.removeEventListener('scroll', this.catchScroll)
  }
}
</script>
