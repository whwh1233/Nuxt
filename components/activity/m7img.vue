<style></style>

<template>
  <section class="banner__row" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <navigator :url="tplData.url" class="banner__el">
      <img class="banner__img" :src="tplData.bgimg" />
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
