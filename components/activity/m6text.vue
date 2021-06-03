<style>
.c-m6__pre {
  width: 90%;
  margin: auto;
  white-space: pre-wrap;
  word-wrap: break-word;
}
</style>

<template>
  <div class="c-m6" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <pre class="c-m6__pre" style="line-height:1.4" :style="[styleObj]">{{ tplData.text }}</pre>
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
      if (this.tplData.center === 'on') {
        return { textAlign: 'center' }
      } else {
        return {}
      }
    }
  }
}
</script>
