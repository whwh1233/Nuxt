<style scoped>
.m21 {
  padding-top: 20px;
  text-align: center;
  overflow-x: auto;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
  background: #fff;
}

.m21__list {
  padding: 0 0 20px 40px;
  font-size: 0;
  white-space: nowrap;
}

.m21__el {
  display: inline-block;
  margin-right: 20px;
  width: 25.78%;
  vertical-align: top;
}

.m21__el:last-of-type {
  margin-right: 40px;
}

.m21__img {
  display: block;
  padding-bottom: 100%;
  width: 100%;
  height: 0;
  border-radius: 10px;
  background-color: #f5f5f5;
  background-repeat: no-repeat;
  background-position: center;
  background-size: contain;
}

.m21__more {
  background-size: cover;
}

.m21__name {
  margin: 10px auto;
  width: 150px;
  font-size: 24px;
  line-height: 1.4;
  white-space: normal;
  word-break: break-all;
}

.m21__price {
  font-size: 0;
  overflow: hidden;
}

.m21__sell,
.m21__sell--b,
.m21__origin,
.m21__line {
  display: inline-block;
  vertical-align: middle;
  font-size: 24px;
}

.m21__sell--b {
  color: #111;
}

.m21__sell {
  color: #f95555;
}

.m21__origin {
  margin-left: 10px;
  color: #888;
  text-decoration: line-through;
}

.m21 .m21__rebate {
  font-size: 21px;
}

.m21__line {
  margin: 0 10px;
  width: 2px;
  height: 22px;
  background: #eee;
}

.m21__hide {
  position: relative;
  width: 100%;
  height: 9px;
  margin-top: -9px;
  background-color: #fff;
  z-index: 100;
}
</style>

<template>
  <div v-if="hasItem">
    <div class="m21" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
      <ul class="m21__list cfix">
        <li v-for="(list, index) in tplData.itemList" :key="index" class="m21__el">
          <navigator :url="list.url" class="brand-item-link">
            <div class="m21__img" :style="{ backgroundImage: 'url(' + list.bgimg + ')' }"></div>
            <h2 class="m21__name line line-2">{{ list.name }}</h2>
            <p class="m21__price cfix">
              <template v-if="list.predictPrice">
                <span class="m21__sell--b">￥{{ list.predictPrice }}</span>
              </template>
              <template v-else>
                <span class="m21__sell--b">￥{{ list.sellPrice }}</span>
              </template>
              <span class="m21__line"></span>
              <span v-if="list.rebate" class="m21__sell m21__rebate">返{{ list.rebate }}</span>
            </p>
          </navigator>
        </li>
        <li v-if="tplData.url" class="m21__el">
          <navigator :url="tplData.url" class="brand-item-link">
            <div class="m21__img m21__more" style="background-image: url(https://pic.wanwustore.cn/FjGFdK_Yfng8lNarwrM9AbmUEYml);"></div>
            <h2 class="m21__name">&nbsp;<br />&nbsp;</h2>
            <p class="m21__price">&nbsp;</p>
          </navigator>
        </li>
      </ul>
    </div>
    <div class="m21__hide"></div>
  </div>
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
  },
  computed: {
    hasItem() {
      return !!this.tplData.itemList
    }
  }
}
</script>
