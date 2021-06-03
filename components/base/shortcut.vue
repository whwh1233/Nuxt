<style>
.shortcut__wrapper {
  position: fixed;
  z-index: 100;
}

.shortcut__btn {
  display: block;
  margin-top: 10px;
  width: 100px;
  height: 100px;
}
</style>

<template>
  <div v-if="!isApp" class="shortcut__wrapper" :style="`right:${right}px;bottom:${bottom}px`">
    <navigator class="shortcut__btn" url="/m/uiww/customerindex">
      <img class="block-image" src="images/shortcut__index.png" />
    </navigator>
    <navigator class="shortcut__btn" url="/m/uiww/cart">
      <img class="block-image" src="images/shortcut__cart.png" />
    </navigator>
  </div>
</template>

<script>
export default {
  props: {
    right: {
      type: Number,
      default: 40
    },
    bottom: {
      type: Number,
      default: 150
    }
  }
}
</script>
