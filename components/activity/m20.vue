<style>
.c-m20__pre {
  width: 90%;
  margin: auto;
  white-space: pre-wrap;
  word-wrap: break-word;
}
</style>

<template>
  <div class="c-m20 cfix" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <pre class="c-m20__pre" style="line-height: 1.4" :style="[styleObj]">{{ tplData.text }}</pre>
  </div>
</template>

<script>
export default {
  props: {
    tplData: {
      type: Object,
      default: {}
    }
  },
  computed: {
    styleObj() {
      let styleObj = {}
      if (this.tplData.center === 'on') {
        styleObj.textAlign = 'center'
      }
      if (this.tplData.fontSize) {
        styleObj.fontSize = this.tplData.fontSize
      }
      if (this.tplData.fontColor) {
        styleObj.color = this.tplData.fontColor
      }
      if (this.tplData.fontWeight) {
        styleObj.fontWeight = this.tplData.fontWeight
      }
      if (this.tplData.paddingTop) {
        styleObj.paddingTop = this.tplData.paddingTop
      }
      if (this.tplData.paddingBottom) {
        styleObj.paddingBottom = this.tplData.paddingBottom
      }
      return styleObj
    }
  }
}
</script>
