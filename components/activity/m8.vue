<style scoped>
.single-item-row {
  margin: 20px 0;
}
.single-item {
  width: 50%;
  margin: auto;
}
</style>

<template>
  <section class="single-item-row" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
    <div class="single-item">
      <element :item="item"></element>
    </div>
  </section>
</template>

<script>
// import itemElement from 'components/item/element'

var Props = {
  tplData: {
    type: Object
  }
}

var ComputedModel = {
  item() {
    return this.tplData.itemList[this.tplData.itemId]
  }
}

var Components = {
  //  itemElement
}

export default {
  props: Props,
  computed: ComputedModel,
  components: Components
}
</script>
