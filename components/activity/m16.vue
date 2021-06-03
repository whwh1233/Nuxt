<style>
.m16__countdown {
  padding: 30px 0;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}
.m16__title {
  position: relative;
  margin-bottom: 15px;
  font-size: 28px;
  color: rgb(0, 0, 0);
  display: inline-block;
  left: 50%;
  transform: translateX(-50%);
}
.m16__title:before,
.m16__title:after {
  position: absolute;
  display: block;
  content: '';
  width: 60px;
  height: 1px;
  border-top: 1px solid;
}
.m16__title:before {
  top: 21px;

  margin-left: -20px;
  transform: translateX(-100%);
}
.m16__title:after {
  top: 21px;
  left: 100%;
  margin-left: 20px;
}
.m16__time {
  padding-left: 6px;
  text-align: center;
  font-size: 0;
}
.m16__time__num {
  display: inline-block;
  width: 40px;
  height: 60px;
  margin-right: 6px;
  color: #fff;
  font-size: 42px;
  line-height: 60px;
  font-family: HelveticaNeue-Bold;
  border-radius: 10px;
}
.m16__time__unit {
  display: inline-block;
  margin: auto 10px auto 14px;
  font-size: 28px;
  font-style: normal;
}
</style>

<template>
  <count-down ref="cd" :time-obj="timeObj">
    <section v-if="diffObj" :style="cdStyle" class="m16__countdown" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId">
      <div :style="{ color: color }" class="m16__title">{{ period === 0 ? beginText : endText }}</div>
      <p class="m16__time">
        <template v-if="diffObj.d">
          <time v-for="(d, index) in diffObj.d" :key="index" track-by="$index" :style="{ backgroundColor: bgColor, color: timeColor }" class="m16__time__num">{{ d }}</time>
          <i :style="{ color: color }" class="m16__time__unit">天</i>
        </template>
        <time :style="{ backgroundColor: bgColor, color: timeColor }" class="m16__time__num">{{ diffObj.h[0] }}</time>
        <time :style="{ backgroundColor: bgColor, color: timeColor }" class="m16__time__num">{{ diffObj.h[1] }}</time>
        <i :style="{ color: color }" class="m16__time__unit">时</i>
        <time :style="{ backgroundColor: bgColor, color: timeColor }" class="m16__time__num">{{ diffObj.m[0] }}</time>
        <time :style="{ backgroundColor: bgColor, color: timeColor }" class="m16__time__num">{{ diffObj.m[1] }}</time>
        <i :style="{ color: color }" class="m16__time__unit">分</i>
        <time :style="{ backgroundColor: bgColor, color: timeColor }" class="m16__time__num">{{ diffObj.s[0] }}</time>
        <time :style="{ backgroundColor: bgColor, color: timeColor }" class="m16__time__num">{{ diffObj.s[1] }}</time>
        <i :style="{ color: color }" class="m16__time__unit">秒</i>
      </p>
    </section>
  </count-down>
</template>
<script>
// import countDown from 'components/common/countdown.vue'
function getTimestamp(t) {
  try {
    t = JSON.parse(t)
    if (t && t.year) {
      return new Date(t.year, t.month - 1, t.day, t.hour, t.minute, t.second).getTime()
    } else {
      throw Error('t is not defined')
    }
  } catch (e) {
    console.log(e)
  }
}
export default {
  data() {
    return {
      cdRef: null
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
    timeObj() {
      return {
        start: ~~(getTimestamp(this.tplData.start) / 1000),
        current: ~~(getTimestamp(this.tplData.current) / 1000),
        end: ~~(getTimestamp(this.tplData.end) / 1000)
      }
    },
    cdStyle() {
      if (this.tplData.bgImg) {
        return {
          backgroundImage: 'url("' + this.tplData.bgImg + '")'
        }
      }
      return {}
    },
    timeColor() {
      return this.tplData.timeColor || '#fff'
    },
    color() {
      return this.tplData.fontColor || '#000'
    },
    beginText() {
      return this.tplData.beginText || '距离活动开始还有'
    },
    endText() {
      return this.tplData.endText || '结束倒计时'
    },
    bgColor() {
      return this.tplData.bgColor || '#000'
    },
    period: function() {
      if (!this.cdRef) return ''
      return this.cdRef.period
    },
    diffObj: function() {
      if (!this.cdRef) return ''
      if (this.period === 2) {
        return {
          h: [0, 0],
          m: [0, 0],
          s: [0, 0]
        }
      }
      var data = this.cdRef.diffObj
      var d
      if (data.d > 0) {
        d = String(data.d).split('')
      }
      return {
        d: d,
        h: ('00' + data.h).slice(-2).split(''),
        m: ('00' + data.m).slice(-2).split(''),
        s: ('00' + data.s).slice(-2).split('')
      }
    }
  },
  components: {
    // countDown
  },
  mounted() {
    this.cdRef = this.$refs.cd
  }
}
</script>
