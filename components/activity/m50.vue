<style></style>

<template>
  <section class="banner__row" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <div @click="goMina" class="banner__el">
      <img class="banner__img" :src="tplData.bgimg" />
    </div>
  </section>
</template>

<script>
// import bridgeUtil from 'utils/bridge'

export default {
  props: {
    tplData: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  methods: {
    goMina() {
      bridgeUtil.navToMina({
        path: this.tplData.path,
        username: this.tplData.username,
        miniprogramtype: this.tplData.miniprogramtype || 0
      })
    }
  }
}
</script>
