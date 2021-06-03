<style>
.top-notice {
  position: fixed;
  left: 0;
  right: 0;
  display: block;
  z-index: 99999;
}

.top-notice-enter-active,
.top-notice-leave-active {
  transition: all 0.3s ease;
}

.top-notice-enter,
.top-notice-leave-to {
  transform: translate3d(0, -100%, 0);
}
</style>

<template>
  <div>
    <transition name="top-notice" appear>
      <div v-show="show" class="top-notice cfix" :style="styleObj">
        <slot></slot>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  props: {
    show: {
      type: Boolean
    },
    styleObj: {
      type: Object
    }
  }
}
</script>
