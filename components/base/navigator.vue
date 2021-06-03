<style></style>

<template>
  <span @click.stop="nav($event)">
    <slot></slot>
  </span>
</template>

<script>
export default {
  props: {
    url: {
      type: String,
      default: ''
    },
    vc: {
      type: String,
      default: ''
    }
  },
  methods: {
    nav(e) {
      if (this.needCountly) {
        let pageX = e.pageX
        let pageY = e.pageY
        let node = e.target
        while (node.tagName !== 'SPAN') {
          node = node.parentNode
        }
        let dataStr = node.getAttribute('self-data')
        if (dataStr) {
          let selfData = JSON.parse(dataStr)
          selfData['pageX'] = pageX
          selfData['pageY'] = pageY
          selfData = JSON.stringify(selfData)
          let obj = {
            selfData,
            prefix: node.getAttribute('prefix')
          }
          this.saveCountlyData(obj, 'countlyClickData')
        }
      }
      this.$emit('navigator', this.url)
      this.navTo(this.url, this.vc)
    }
  }
}
</script>
