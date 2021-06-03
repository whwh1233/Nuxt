<template>
  <div :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <video style="display:block" width="100%" height="100%" preload="none" controls="controls" webkit-playsinline :src="tplData.video" :poster="tplData.imgbg"></video>
  </div>
</template>

<script>
export default {
  props: {
    tplData: {
      type: Object,
      default: {}
    }
  }
}
</script>
