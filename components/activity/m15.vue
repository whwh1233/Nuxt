<template>
  <navigator :url="tplData.url">
    <img :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId" class="foot-banner bon-footer-bar" :src="tplData.bgimg" :bon-uri="tplData.url" />
  </navigator>
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
