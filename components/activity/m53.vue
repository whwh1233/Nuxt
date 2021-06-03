<style>
.m53 {
  position: fixed;
  right: 20px;
  bottom: 150px;
  z-index: 2001;
}
</style>

<template>
  <div class="m53">
    <template v-if="fab">
      <navigator :url="fab.uri">
        <img :src="fab.picUrl" />
      </navigator>
    </template>
  </div>
</template>

<script>
export default {
  data() {
    return {}
  },
  computed: {
    fab() {
      if (!this.tplData || !this.tplData.fab || !this.tplData.fab.picUrl) {
        return
      }
      return this.tplData.fab
    }
  },
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  mounted() {
    if (this.fab) {
      if (window.location.href.toLowerCase().indexOf('customerindex') < 0) {
        let $shortcut = document.querySelector('.shortcut__wrapper')
        $shortcut && $shortcut.remove()
      }

      let $tops = document.querySelectorAll('.back-to-top')
      if ($tops.length > 0) {
        $tops[$tops.length - 1].remove()
      }
    }
  }
}
</script>
