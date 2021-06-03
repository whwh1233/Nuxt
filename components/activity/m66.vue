<style>
.m66 {
  padding: 0 15px;
  overflow: hidden;
}

.m66__el__wrapper {
  float: left;
  padding: 5px;
  box-sizing: border-box;
}
.m66__wrapper--1 {
  width: 100%;
}
.m66__wrapper--2 {
  width: 50%;
}
.m66__wrapper--3 {
  width: 33.333%;
}
.m66__wrapper--4 {
  width: 25%;
}
.m66__el {
  display: block;
  background: #fff;
  border-radius: 24px;
  overflow: hidden;
}
.m66__el--1 {
  display: flex;
  align-items: stretch;
}

.m66__img {
  position: relative;
  background: no-repeat center/cover;
}
.m66__img:after {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: 1;
  background: rgba(0, 0, 0, 0.05);
}
.m66__img--1 {
  width: 350px;
  height: 350px;
  border-radius: 24px 0 0 24px;
}
.m66__img--1:after {
  border-radius: 24px 0 0 24px;
}
.m66__img--2,
.m66__img--3,
.m66__img--4 {
  width: 100%;
  height: 0;
  padding-bottom: 100%;
  border-radius: 24px 24px 0 0;
}
.m66__img--2:after,
.m66__img--3:after,
.m66__img--4:after {
  border-radius: 24px 24px 0 0;
}

.m66__info {
  position: relative;
  box-sizing: border-box;
  z-index: 2;
}
.m66__info--1 {
  flex: 1;
  padding: 20px;
  border-radius: 0 24px 24px 0;
  background: url('https://pic.bbtkids.cn/FpIcnR5M_wJvvImmoeEJykrRwQ-O') no-repeat center right/auto 100%;
}
.m66__info--2 {
  margin-top: -20px;
  height: 244px;
  border-radius: 0 0 24px 24px;
  background: url('https://pic.bbtkids.cn/Fr9ILuG1YI3XSMcjyOCKib9n0D45') no-repeat center bottom/100% 100%;
}
.m66__info--3 {
  margin-top: -26px;
  height: 208px;
  border-radius: 0 0 24px 24px;
  background: url('https://pic.bbtkids.cn/FuuBmTTl-uLg_imwIEzwazmunQan') no-repeat center bottom/100% 100%;
}
.m66__info--4 {
  margin-top: -26px;
  height: 100px;
  border-radius: 0 0 24px 24px;
  background: url('https://pic.bbtkids.cn/Fpo4nmo3sAvnuiz6Hd-ycQBL1gXM') no-repeat center bottom/100% 100%;
}

.m66__logo {
  display: block;
  box-sizing: border-box;
}
.m66__logo--1 {
  height: 100px;
  background: #fff no-repeat left center/auto 100%;
}
.m66__logo--2,
.m66__logo--3,
.m66__logo--4 {
  position: absolute;
  left: 0;
  right: 0;
  margin: auto;
  z-index: 3;
  border: 2px solid #eee;
  background: #fff no-repeat center/contain;
}
.m66__logo--2 {
  top: 0;
  /* width: 33vw; */
  height: 14.67vw;
  max-height: 110px;
  border-radius: 25px;
  transform: translateY(-48%);
}
.m66__logo--3 {
  top: 0;
  /* width: 24vw; */
  height: 10.67vw;
  max-height: 80px;
  border-radius: 20px;
  transform: translateY(-48%);
}
.m66__logo--4 {
  top: 0;
  /* width: 24vw; */
  height: 9.33vw;
  max-height: 70px;
  border-radius: 22px;
  transform: translateY(-48%);
}

.m66__title {
  color: #555;
  font-size: 24px;
  font-family: PingFangSC-Light, PingFangTC-Light, PingFangHK-Light, sans-serif;
  font-weight: 300;
}
.m66__title--1 {
  margin-top: 10px;
}
.m66__title--2,
.m66__title--3,
.m66__title--4 {
  padding: 0 20px;
  text-align: center;
}
.m66__title--2 {
  margin-top: 60px;
  height: 32px;
  line-height: 32px;
}
.m66__title--3 {
  margin-top: 45px;
  height: 30px;
  font-size: 22px;
  line-height: 30px;
}
.m66__title--4 {
  margin-top: 28px;
  height: 30px;
  font-size: 18px;
  line-height: 30px;
}

.m66__txts {
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 100%;
  color: #e64646;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: 600;
}
.m66__txts--1 {
  margin-top: 10px;
  font-size: 32px;
  height: 90px;
  line-height: 45px;
}
.m66__txts--2 {
  margin-top: 8px;
  padding: 0 10px;
  height: 80px;
  font-size: 30px;
  line-height: 40px;
  text-align: center;
  box-sizing: border-box;
}
.m66__txts--3 {
  margin-top: 8px;
  padding: 0 5px;
  height: 60px;
  font-size: 25px;
  line-height: 30px;
  text-align: center;
  box-sizing: border-box;
}
.m66__txts--4 {
  margin-top: 2px;
  padding: 0 5px;
  height: 30px;
  font-size: 22px;
  line-height: 30px;
  text-align: center;
  box-sizing: border-box;
}

.m66__link {
  position: absolute;
  width: 38px;
  height: 38px;
  background: url('data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACYAAAAnCAMAAABUv8o5AAAAolBMVEUAAAD/YGD/bGz/amr/Z2f/Zmb/amr/Y2P/ZGT/aWn+Z2f6VVX6Vlb7WFj6VFT6VVX6VFT6WVn/X1/5VVX5VVX5VVX6VVX6VVX6Vlb8W1v5VFT7WFj6VVX6V1f6V1f6Vlb/ZWX/Zmb5VVX////5ZWX7mZn+9vb7qan7oKD6g4P+6+v94+P92tr9z8/8w8P8t7f6i4v5cHD5XFz+8fH6jo76eHjiPS1vAAAAInRSTlMAAwcSChcPDCAcJvyZhffx6l4T5uHcy7yhV6mRkG1qZSsjDF3qjQAAAYhJREFUOMu10dlywiAUBuAGkkA2zWJM4i6o1S7a9f1frUcSBBLsRWf63zHzzfkP8PCPcSAoz5ED+QXl61kZMRaVs3UO0I5oPGK3jGJqgVC2HDMj4yWU9xWJ2SAxAWeqillSgTMaY2ZNrPc6aMXuZIUcpaja/niMjHtQcJItmMye89cP3S0kg3dXw9445y87fVzeOcfNmMojuGfdZa7TDiO13rIH9/SuzjVBjmD+lOn5OnD++c1kpr5kKTNyAne4zUs75mL142q/ozyMsKvYYLtdjyGCofT+XVNMUMuMK1x6LzcF1pbGmjrz3j/Et90ac6+z8atNx5AfpPpnXZieNJDvRrxEe7QTM5J4RDIcFuxOihALJlq9LLKrKPNEZzcuSOwsCdphchytbaqmYphkLrgkGjQmoFxgymGPZhNTTTLqYankeuA2yURDyQYUAaUx0RvQsJlXZVGU1bwJaSAaJVMOA9yGIltAWCm9V0AvEPEEko2Gu0LiYxGfXJFUQwgUgpBCdinz8Jf8ANr5YsCQGV1FAAAAAElFTkSuQmCC')
    no-repeat center/contain;
}
.m66__link--1 {
  bottom: 27px;
  left: 23px;
}
.m66__link--2,
.m66__link--3 {
  left: 0;
  right: 0;
  bottom: 14px;
  margin: auto;
}
.m66__link--3 {
  width: 30px;
  height: 30px;
  left: 0;
  right: 0;
  bottom: 14px;
  margin: auto;
}
.m66__link--4 {
  width: 30px;
  height: 30px;
  left: 0;
  right: 0;
  bottom: 10px;
  margin: auto;
}
</style>

<template>
  <div class="m66">
    <div class="m66__el__wrapper" :class="'m66__wrapper--' + column" v-for="(item, i) in itemList" :key="i">
      <navigator class="m66__el" :class="'m66__el--' + column" :url="item.jumpUrl">
        <div class="m66__img" :class="'m66__img--' + column" :style="{ backgroundImage: 'url(' + item.picUrl + ')' }"></div>
        <div class="m66__info cfix" :class="'m66__info--' + column">
          <img v-if="item.logoPic && column !== '4'" :src="item.logoPic" class="m66__logo" :class="'m66__logo--' + column" />
          <!-- <div class="m66__logo" :class="'m66__logo--' + column" :style="{ backgroundImage: 'url(' + item.logoPic + ')' }"></div> -->
          <p class="m66__title line line-1" :class="'m66__title--' + column">{{ item.title }}</p>
          <div class="m66__txts" :class="'m66__txts--' + column">
            <div v-if="item.sellPoint1" class="m66__txt line line-1">{{ item.sellPoint1 }}</div>
            <div v-if="item.sellPoint2 && column !== '4'" class="m66__txt line line-1">{{ item.sellPoint2 }}</div>
          </div>
          <div v-if="column !== '4'" class="m66__link" :class="'m66__link--' + column"></div>
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
  computed: {
    column() {
      return this.tplData.column || 1
    },
    itemList() {
      return this.tplData.itemList || []
    }
  }
}
</script>
