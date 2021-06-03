<style></style>

<template>
  <div>
    <slot></slot>
  </div>
</template>

<script>
var PERIOD = {
  PRE: 0,
  ON: 1,
  FINISH: 2
}
export default {
  data() {
    return {
      start: this.timeObj.start,
      current: this.timeObj.current,
      end: this.timeObj.end,
      ms: 9
    }
  },
  props: {
    timeObj: {
      type: Object
    }
  },
  computed: {
    period() {
      if (this.current < this.start) {
        return PERIOD.PRE
      } else if (this.current < this.end) {
        return PERIOD.ON
      } else {
        return PERIOD.FINISH
      }
    },
    diffTime() {
      return [this.start - this.current, this.end - this.current, this.current - this.end]
    },
    diffObj() {
      var _diff = this.diffTime[this.period]
      var _d = ~~(_diff / 86400)
      var _H = ~~(_diff / 3600)
      var _h = ~~((_diff = _diff % 86400) / 3600)
      var _m = ~~((_diff = _diff % 3600) / 60)
      var _s = _diff % 60
      return { d: _d, h: _h, H: _H, m: _m, s: _s }
    },
    diffMsObj() {
      return { ms: this.ms }
    }
  },
  watch: {
    period(newVal, oldVal) {
      console.log('watch period:' + newVal)
      // this.$emit('changeflash', newVal)
    },
    timeObj(newVal, oldVal) {
      this.reset()
    }
  },
  methods: {
    msTimerFunc() {
      this.ms--
      this.ms < 0 && (this.ms = 9)
    },
    run() {
      this.lag = ~~(Date.now() / 1000) - this.current
      this.timer = setInterval(() => {
        if (this.end <= this.current) {
          clearInterval(this.timer)
          clearInterval(this.msTimer)
        } else {
          clearInterval(this.msTimer)
          this.ms = 9
          this.current = ~~(Date.now() / 1000) - this.lag
          this.msTimer = setInterval(this.msTimerFunc, 100)
        }
      }, 1000)
    },
    reset() {
      this.$nextTick(() => {
        this.start = this.timeObj.start
        this.current = this.timeObj.current
        this.end = this.timeObj.end
        this.run()
      })
    }
  },
  mounted() {
    this.run()
  }
}
</script>
