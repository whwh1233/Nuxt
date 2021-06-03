<style>
.m67 {
  padding: 0 2.66vw;
  text-align: center;
}
.m67.m67__ani {
  padding: 0.53vw 2.66vw;
}

.m67__el__wrapper {
  position: relative;
  display: inline-block;
  vertical-align: top;
  margin-top: 1.333vw;
}

.m67__el {
  border-radius: 30px;
  overflow: hidden;
  /*background: #fff;*/
}

/** 1 */
.m67__el__wrapper--1 {
  width: 100%;
}
.m67__el--1 {
  display: flex;
  flex-direction: row-reverse;
  width: 100%;
  height: 30.67vw;
  text-align: left;
  background: #fff;
}

/** 2 */
.m67__el__wrapper--2 {
  margin-right: 1.6vw;
  width: calc(50% - 0.8vw);
  height: 62.67vw;
}
.m67__el__wrapper--2:nth-of-type(2n + 2) {
  margin-right: 0;
}

/** 3 */
.m67__el__wrapper--3 {
  margin-right: 1.33vw;
  width: 32vw;
}
.m67__el__wrapper--3.m67__el--sm {
  margin-top: 3.86vw;
  width: 28vw;
}
.m67__el__wrapper--3:nth-of-type(3n + 3) {
  margin-right: 0;
}
.m67__ani .m67__el__wrapper--3:nth-of-type(3n + 1),
.m67__ani .m67__el__wrapper--3:nth-of-type(3n + 3) {
  animation: aniDown 5s infinite;
}
.m67__ani .m67__el__wrapper--3:nth-of-type(3n + 2) {
  animation: aniUp 5s infinite;
}

/** 4 */
.m67__el__wrapper--4 {
  margin-right: 1.33vw;
  width: 24.53vw;
  /* height: 28.67vw; */
}
.m67__el__wrapper--4.m67__el--sm {
  margin-top: 3.73vw;
  width: 20.8vw;
  /* height: 30.93vw; */
}
.m67__el__wrapper--4:nth-of-type(4n + 4) {
  margin-right: 0;
}
.m67__ani .m67__el__wrapper--4:nth-of-type(4n + 1),
.m67__ani .m67__el__wrapper--4:nth-of-type(4n + 3) {
  animation: aniDown 5s infinite;
}
.m67__ani .m67__el__wrapper--4:nth-of-type(4n + 2),
.m67__ani .m67__el__wrapper--4:nth-of-type(4n + 4) {
  animation: aniUp 5s infinite;
}

/* 角标 */
.m67__logo {
  position: absolute;
  top: -0.8vw;
  right: -0.8vw;
  z-index: 10;
}
.m67__logo--1,
.m67__logo--2 {
  width: 10.67vw;
  /* height: 10.67vw;*/
}
.m67__el--lg .m67__logo--3 {
  width: 9.07vw;
  /* height: 9.07vw;*/
}
.m67__el--lg .m67__logo--4 {
  width: 8.53vw;
  /* height: 8.53vw;*/
}
.m67__el--sm .m67__logo--3 {
  width: 8vw;
  /* height: 8vw;*/
}
.m67__el--sm .m67__logo--4 {
  width: 7.2vw;
  /* height: 7.2vw;*/
}

/* 头图 */
.m67__img {
  width: 100%;
  padding-bottom: 100%;
  background: no-repeat center/cover;
}
.m67__img--1 {
  padding: 0;
  width: 40vw;
  height: 30.67vw;
  background: no-repeat right center/auto 100%;
}

/* 文字区域 */
.m67__info {
  box-sizing: border-box;
}
.m67__info--1 {
  flex: 1;
  display: flex;
  flex-direction: column-reverse;
  justify-content: flex-end;
  padding: 3vw 0 0 11.86vw;
  background: url('https://pic.bbtkids.cn/FjqSQ-j8QknqSgE89oS6T6P6sINo'), url('https://pic.bbtkids.cn/FqTF_QWVIcec2R1KiiFJNJLnfUVk');
  background-repeat: no-repeat;
  background-size: auto 101%, 16vw 5.06vw;
  background-position: left center, 12vw 22vw;
}
.m67__info--2 {
  margin-top: -3.6vw;
  padding: 3.2vw 10px 0;
  height: 19.46vw;
  background: url('https://pic.bbtkids.cn/FpDQvuNAJGAVp7NgAuFO6Dq98KJM') no-repeat center/cover;
}
.m67__el--lg .m67__info--3 {
  margin-top: -4.8vw;
  padding: 2.26vw 10px 0;
  height: 14.8vw;
  background: url('https://pic.bbtkids.cn/FgQNVsYvk9tk4AKq36dqyIVIyebV') no-repeat center/cover;
}
.m67__el--sm .m67__info--3 {
  margin-top: -4.26vw;
  padding: 2.26vw 10px 0;
  height: 13.33vw;
  background: url('https://pic.bbtkids.cn/FiItNBQFXdkgndVDaUXHFvaROB5g') no-repeat center/cover;
}

.m67__el--lg .m67__info--4 {
  margin-top: -2.13vw;
  padding: 2.26vw 10px 0;
  height: 13.67vw;
  background: url('https://pic.bbtkids.cn/Fk79oE24pXfy-67QbcmDl3ghH6tc') no-repeat center/cover;
}
.m67__el--sm .m67__info--4 {
  margin-top: -1.73vw;
  padding: 2.26vw 10px 0;
  height: 11.73vw;
  background: url('https://pic.bbtkids.cn/FsI6FZOe6g5QGuZCGPUPP5RfwM6F') no-repeat center/cover;
}

.m67__time {
  color: #ddd;
}
.m67__sellpoint {
  color: #e64646;
  font-family: PingFangSC-Semibold, PingFangTC-Semibold, PingFangHK-Semibold, sans-serif;
  font-weight: 600;
}
.m67__title {
  color: #fff;
  font-family: PingFangSC-Medium, PingFangTC-Medium, PingFangHK-Medium, sans-serif;
  font-weight: 500;
}

.m67__time--1 {
  margin-top: 6px;
  color: #666;
  font-size: 22px;
}
.m67__sellpoint--1 {
  font-size: 34px;
}
.m67__title--1 {
  color: #111;
}
.m67__time--2 {
  font-size: 22px;
}
.m67__sellpoint--2 {
  font-size: 32px;
}
.m67__title--2 {
  font-size: 26px;
}

.m67__time--3 {
  font-size: 18px;
  line-height: 25px;
}
.m67__sellpoint--3 {
  margin-top: -2px;
  font-size: 27px;
  line-height: 38px;
}
.m67__title--3 {
  font-size: 21px;
  line-height: 29px;
}
.m67__el--sm .m67__time--3 {
  font-size: 15px;
  line-height: 21px;
}
.m67__el--sm .m67__sellpoint--3 {
  margin-top: -2px;
  font-size: 24px;
  line-height: 33px;
}
.m67__el--sm .m67__title--3 {
  font-size: 18px;
  line-height: 25px;
}

.m67__time--4 {
  font-size: 17px;
}
.m67__sellpoint--4 {
  font-size: 22px;
}
.m67__title--4 {
  font-size: 19px;
}
.m67__el--sm .m67__time--4 {
  font-size: 14px;
}
.m67__el--sm .m67__sellpoint--4 {
  font-size: 18px;
}
.m67__el--sm .m67__title--4 {
  font-size: 17px;
}

.randAni {
  animation: aniScale 1.5s forwards;
}
@keyframes aniScale {
  0% {
    transform: scale3D(0, 0, 1);
  }
  55% {
    transform: scale3D(1.02, 1.02, 1);
  }
  70% {
    transform: scale3D(0.99, 0.99, 1);
  }
  85% {
    transform: scale3D(1.005, 1.005, 1);
  }
  100% {
    transform: scale3D(1, 1, 1);
  }
}
@keyframes aniDown {
  0% {
    transform: translate3D(0, -0.8vw, 0);
  }
  50% {
    transform: translate3D(0, 0.8vw, 0);
  }
  100% {
    transform: translate3D(0, -0.8vw, 0);
  }
}
@keyframes aniUp {
  0% {
    transform: translate3D(0, 0.8vw, 0);
  }
  50% {
    transform: translate3D(0, -0.8vw, 0);
  }
  100% {
    transform: translate3D(0, 0.8vw, 0);
  }
}
</style>

<template>
  <div class="m67" :class="{ m67__ani: useAni }">
    <navigator class="m67__el__wrapper" v-for="(item, i) in itemList" :key="i" :url="item.jumpUrl" :class="'m67__el__wrapper--' + column + (item.lg ? ' m67__el--lg' : ' m67__el--sm')">
      <div :class="aniList[i] ? 'randAni' : ''">
        <img v-if="item.logoPic" :src="item.logoPic" class="m67__logo" :class="'m67__logo--' + column" />
        <div class="m67__el" :class="'m67__el--' + column">
          <div class="m67__img" :class="'m67__img--' + column" :style="item.picUrl ? { backgroundImage: 'url(' + item.picUrl + ')' } : ''"></div>
          <div class="m67__info cfix" :class="'m67__info--' + column">
            <p class="m67__time line line-1" :class="'m67__time--' + column">{{ item.time }}</p>
            <p class="m67__sellpoint line line-1" :class="'m67__sellpoint--' + column">{{ item.sellPoint }}</p>
            <p class="m67__title line line-1" :class="'m67__title--' + column">{{ item.title }}</p>
          </div>
        </div>
      </div>
    </navigator>
  </div>
</template>

<script>
export default {
  data() {
    return {
      aniList: []
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
  computed: {
    column() {
      return +(this.tplData.column || 1)
    },
    useAni() {
      if (this.column <= 2) return false
      return this.tplData.animate === 'on'
    },
    itemList() {
      let list = this.tplData.itemList || []
      return list.map((one, i) => {
        if (this.column === 3) {
          one.lg = i % 2 === 0
        } else if (this.column === 4) {
          let r = i % 8
          one.lg = r === 0 || r === 2 || r === 5 || r === 7
        }
        return one
      })
    }
  },
  methods: {
    runRandAni() {
      let row = Math.ceil(this.itemList.length / this.column)
      let list = this.aniList.map(i => 0)
      for (let i = 0; i < row; i++) {
        let aniIndex = ((Math.random() * this.column) | 0) + i * this.column
        list[aniIndex] = 1
      }
      this.aniList = list
    }
  },
  mounted() {
    if (this.column >= 3 && this.useAni) {
      this.aniList.length = this.itemList.length
      this.aniList.fill(0)
      setInterval(() => {
        this.runRandAni()
      }, 5000)
    }
  }
}
</script>
