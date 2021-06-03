<style></style>

<template>
  <section class="banner__row" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <navigator v-for="(banner, index) in tplData.bannerList" :key="index" :url="banner.url" class="banner__el">
      <img class="banner__img" :src="banner.bgimg" />
    </navigator>
  </section>
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
