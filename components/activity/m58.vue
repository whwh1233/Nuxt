<style scoped>
.m58 {
  text-align: center;
  position: absolute;
  bottom: 67px;
  box-sizing: border-box;
  padding: 0px 2.7%;
  width: 100%;
}

.m58__list {
  overflow-x: auto;
  overflow-y: hidden;
  -webkit-overflow-scrolling: touch;
  font-size: 0;
  white-space: nowrap;
}

.m58__el {
  display: inline-block;
  margin-right: 20px;
  width: 23.4%;
  vertical-align: top;
  background-color: #fff;
  border-radius: 40px;
  overflow: hidden;
  padding-bottom: 8px;
}

.m58__el:first-of-type {
  margin-left: 4%;
}

.m58__img {
  display: block;
  padding-bottom: 108.43%;
  width: 100%;
  height: 0;
  background: #fff no-repeat center/cover;
}

.m58__more {
  opacity: 0;
}

.m58__name {
  margin: 2px auto 0px;
  padding: 0px 10px;
  font-size: 18px;
  color: #888888;
  white-space: normal;
  word-break: break-all;
}

.m58__price {
  overflow: hidden;
}

.m58__sell,
.m58__sell--b,
.m58__origin,
.m58__line {
  display: inline-block;
  vertical-align: middle;
  font-size: 24px;
}

.m58__sell--b {
  color: #111;
}

.m58__sell {
  color: #ff0000;
  font-weight: 600;
  font-family: PingFang SC, sans-serif;
}

.m58__origin {
  margin-left: 10px;
  color: #888;
  text-decoration: line-through;
}

.m58 .m58__rebate {
  font-size: 21px;
}

.m58__line {
  margin: 0 10px;
  width: 2px;
  height: 22px;
  background: #eee;
}

.m58__hide {
  position: relative;
  width: 100%;
  height: 9px;
  margin-top: -9px;
  background-color: #fff;
  z-index: 100;
}
.m58__bg {
  width: 100%;
  height: 0px;
  display: block;
  padding-bottom: 85.07%;
  background-position: center;
  background-size: contain;
  position: relative;
  overflow: hidden;
}
.m58__el--more {
  display: inline-block;
  margin-right: 20px;
  width: 23.4%;
  vertical-align: top;
  border-radius: 40px;
  overflow: hidden;
  padding-bottom: 8px;
  background: url(https://pic.bbtkids.cn/Fur43lS1FyfPseat-IvlZi7_2dEE) center/cover;
}
</style>

<template>
  <navigator :url="tplData.bgUri">
    <div class="m58__bg" :style="{ backgroundImage: 'url(' + tplData.bgPic + ')' }">
      <div v-if="hasItem">
        <div class="m58" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
          <ul class="m58__list cfix">
            <li v-for="(list, index) in tplData.itemInfoList" :key="index" class="m58__el">
              <navigator :url="`/m/uiww/getSellItem?itemId=${list.itemId}`" :vc="`sellitemvc&itemId=${list.itemId}`" class="brand-item-link">
                <div class="m58__img" :style="{ backgroundImage: 'url(' + list.picUrl + ')' }"></div>
                <h2 class="m58__name line line-1">{{ list.name }}</h2>
                <p class="m58__price cfix">
                  <template v-if="list.predictPrice">
                    <span class="m58__sell">￥{{ list.predictPrice }}</span>
                    <!-- <del class="m58__origin">￥{{list.originPrice}}</del> -->
                  </template>
                  <template v-else>
                    <span class="m58__sell">￥{{ list.sellPrice }}</span>
                    <!-- <del v-if="(list.originPrice - list.sellPrice) > 0 " class="m58__origin">￥{{list.originPrice}}</del> -->
                  </template>
                </p>
              </navigator>
            </li>
            <li v-if="tplData.bgUri" class="m58__el--more">
              <navigator :url="tplData.bgUri" class="brand-item-link">
                <div class="m58__img m58__more"></div>
                <h2 class="m58__name">&nbsp;</h2>
                <p class="m58__price"><span class="m58__sell">&nbsp;</span></p>
              </navigator>
            </li>
          </ul>
        </div>
        <div class="m58__hide"></div>
      </div>
    </div>
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
  },
  computed: {
    hasItem() {
      return !!this.tplData.itemInfoList
    }
  },
  mounted() {
    // console.log(this.tplData)
  }
}
</script>
