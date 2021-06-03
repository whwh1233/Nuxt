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
  <!-- 删除v-if： v-if="!isApp"  TODO  -->
  <!-- :style="`right:${right}px;bottom:${bottom}px`" -->
  <div class="shortcut__wrapper" :style="{ right: right, bottom: bottom }">
    <navigator class="shortcut__btn" url="/m/uiww/customerindex">
      <img class="block-image" src="~/assets/images/shortcut__index.png" />
    </navigator>
    <navigator class="shortcut__btn" url="/m/uiww/cart">
      <img class="block-image" src="~/assets/images/shortcut__cart.png" />
    </navigator>
  </div>
</template>

<script>
export default {
  props: {
    right: {
      type: String,
      default: '40px'
    },
    bottom: {
      type: String,
      default: '150px'
    }
  }
}
</script>
