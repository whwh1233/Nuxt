<style>
.swiper-slide {
  height: 100%;
}

.m44-swiper-container {
  position: relative;
  width: 100%;
  overflow: hidden;
}

.m44-slide-img {
  display: block;
  margin: 0 auto;
}

.m44-swiper-pagination {
  position: absolute;
  z-index: 20;
  bottom: 10px;
  width: 100%;
  text-align: center;
}

.m44-bullet-active {
  opacity: 1 !important;
  background-color: #000 !important;
}

.m44-bullet {
  width: 16px;
  height: 16px;
  display: inline-block;
  border-radius: 100%;
  margin-left: 10px;
  background-color: #aaa;
}

.m44__link {
  display: block;
  border: 10px solid gold;
  box-sizing: border-box;
}
</style>

<template>
  <div class="m44">
    <p>这是m44组件，暂时先注释掉</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      swiper: null
    }
  }
}
</script>
