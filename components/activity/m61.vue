<style>
.m61 {
  margin: 20px 20px 0px 20px;
  padding: 10px 10px;
  border-radius: 56px;
  background-color: #fff;
  overflow: hidden;
}
.m61__ele {
  position: relative;
  margin-bottom: 40px;
}
.m61__ele__wrapper {
  display: block;
}
.m61__itempic {
  position: relative;
  width: 100%;
  height: 0px;
  padding-top: 49.85%;
  border-radius: 50px;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}
.m61__item__soldout {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  margin: auto;
  width: 188px;
  height: 188px;
  border-radius: 50%;
  background-image: url('https://pic.bbtkids.cn/FqS8OuOlTgUs-dGWFFSO4N3n0LDm');
}

.m61__tag {
  position: absolute;
  top: 35px;
  left: -3px;
  color: #fff;
  background-color: #fd575e;
  border-radius: 8px;
  height: 36px;
  line-height: 36px;
  padding: 0px 16px;
  font-size: 20px;
  z-index: 100;
}
.m61__info {
  margin-top: 20px;
  padding: 0px 14px;
}
.m61__sellpoint {
  display: block;
  font-family: PingFangSC-Medium;
  font-weight: 500;
  font-size: 30px;
  color: #111111;
  margin-bottom: 8px;
}
.m61__itemname {
  color: #aaaaaa;
  font-size: 24px;
}
.m61__price {
  margin-top: 17px;
  display: flex;
  align-items: baseline;
}
.m61__sellprice {
  font-size: 42px;
  font-family: PingFangSC-Semibold;
  font-weight: 600;
  color: #000000;
}
.m61__sellprice::before {
  content: '';
  display: inline-block;
  width: 32px;
  height: 29px;
  background-image: url('https://pic.bbtkids.cn/FgsYooULfPIYmJjpCt0Yl4XUjPjb');
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
}
.m61__earnprice {
  color: #f95555;
  font-size: 26px;
  margin-left: 18px;
}
.m61__single__btn {
  padding: 0 16px;
  height: 48px;
  font-size: 20px;
  line-height: 48px;
  text-align: center;
  border-radius: 24px;
  box-sizing: border-box;
  background: linear-gradient(135deg, rgba(252, 88, 78, 1) 0%, rgba(253, 86, 103, 1) 100%);
  box-shadow: 0px 4px 12px 0px rgba(255, 118, 118, 0.54);
  position: absolute;
  right: 10px;
  bottom: 7px;
  color: #fff;
}
.m61__originprice {
  margin-left: -2px;
  color: #aaaaaa;
  font-size: 28px;
  font-family: PingFangSC-Regular;
  font-weight: normal;
  text-decoration: line-through;
}
</style>
<template>
  <div>
    <div class="m61">
      <navigator :url="`/m/uiww/getSellItem?itemId=${item.itemId}`" :vc="`sellitemvc&itemId=${item.itemId}`" v-for="(item, index) in tplData.itemList" :key="index" class="m61__ele__wrapper">
        <div class="m61__ele">
          <div class="m61__tag" v-if="item.tag">{{ item.tag }}</div>
          <div class="m61__itempic" :style="{ backgroundImage: 'url(' + item.picUrl + ')' }">
            <div class="m61__item__soldout div-bg" v-if="item.soldOut"></div>
          </div>
          <div class="m61__info">
            <div class="m61__sellpoint line line-2" v-if="item.sellingPoint">{{ item.sellingPoint }}</div>
            <div class="m61__itemname line line-2">{{ item.name }}</div>
            <div class="m61__price">
              <p class="m61__sellprice">
                {{ item.predictPrice || item.sellPrice }} <span class="m61__originprice" v-if="item.originPrice">￥{{ item.originPrice }}</span>
              </p>
              <p class="m61__earnprice" v-if="item.rebate">返{{ item.rebate }}</p>
            </div>
            <div class="m61__single__btn">立即抢购</div>
          </div>
        </div>
      </navigator>
    </div>
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
  created() {}
}
</script>
