<style>
.act-coupon {
  display: block;
  width: 100%;
}
</style>

<template>
  <div>
    <img @click.stop="getCoupon" class="act-coupon" :src="bgImg" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId" />
    <!-- <login ref="login" @login-succ="loginSucc"></login> -->
    <count-down v-if="timeObj" ref="cd" :time-obj="timeObj"></count-down>
  </div>
</template>

<script>
function timeFormat(time) {
  time = JSON.parse(time)
  let str = `${time.year}/${time.month}/${time.day} ${time.hour}:${time.minute}:${time.second}`
  // alert(str)
  let date = new Date(str)
  return ~~(date.getTime() / 1000)
}
// import API from 'api/api'
// import login from 'components/login/login'
// import countDown from 'components/common/countdown'
export default {
  data() {
    return {
      busy: false,
      cdComp: null
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
  watch: {
    period(newVal, oldVal) {
      console.log('period change')
    }
  },
  computed: {
    loginComp() {
      return this.$refs.login
    },
    period() {
      if (this.cdComp) {
        return this.cdComp.period
      }
    },
    bgImg() {
      if (this.period === 0) {
        return this.tplData.preimg
      }
      if (this.period === 1) {
        return this.tplData.actimg
      }
      if (this.period === 2) {
        return this.tplData.afterimg
      }
    },
    timeObj() {
      return {
        start: timeFormat(this.tplData.start),
        current: ~~(new Date().getTime() / 1000),
        end: timeFormat(this.tplData.end)
      }
    },
    param() {
      return {
        mode: 'getmycoupon',
        connid: this.tplData.connId,
        actid: this.$parent.activityInfo.id,
        belongNew: this.tplData.belongNew == true || this.tplData.belongNew == 'on' ? true : false
      }
    }
  },
  components: {
    // login,
    // countDown,
  },
  methods: {
    async getCoupon() {
      if (this.busy || this.period !== 1) return
      this.busy = true
      try {
        let res = await this.request.post(API.actgetdata, this.param)
        res = res.data
        if (!res) {
          return alert('获取优惠券失败，请重试！')
        }
        var errno = res.errno
        switch (errno) {
          case 0:
            return alert('领取成功！')
          case 201:
            this.loginComp.login(window.location.href)
            break
          case 202019:
            break
          case 230016:
            throw new Error()
          default:
            alert(res.errmsg)
        }
      } catch (e) {
        alert('获取优惠券失败，请重试！')
      } finally {
        this.busy = false
      }
    },
    loginSucc() {
      this.getCoupon()
    }
  },
  mounted() {
    this.cdComp = this.$refs.cd
    // alert()
  }
}
</script>
