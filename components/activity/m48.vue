<style>
.m48 {
  padding: 0 50px;
  width: 100%;
  line-height: 2;
  box-sizing: border-box;
  overflow: hidden;
}

.m48 strong {
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: bolder;
}
</style>

<template>
  <div class="m48" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <div v-html="tplData.content"></div>
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
  }
}
</script>
