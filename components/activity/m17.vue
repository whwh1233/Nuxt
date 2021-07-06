<style>
.act-coupon {
  display: block;
  width: 100%;
}
</style>

<template>
  <div>
    <img @click.stop="getCoupon" class="act-coupon" :src="tplData.bgimg" :data-sort="tplData.sort" :data-anchor-id="tplData.anchorId" />
    <!-- <login ref="login" @login-succ="loginSucc"></login> -->
  </div>
</template>

<script>
// import API from 'api/api'
// import login from 'components/login/login'

export default {
  data() {
    return {
      busy: false
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
    loginComp() {
      return this.$refs.login
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
  },
  methods: {
    // async getCoupon() {
    //   if (this.busy) return
    //   this.busy = true
    //   try {
    //     let res = await this.request.post(API.actgetdata, this.param)
    //     res = res.data
    //     if (!res) {
    //       return alert('获取优惠券失败，请重试！')
    //     }
    //     var errno = res.errno
    //     switch (errno) {
    //       case 0:
    //         return alert('领取成功！')
    //       case 201:
    //         this.loginComp.login(window.location.href)
    //         break
    //       case 202019:
    //         break
    //       case 230016:
    //         throw new Error()
    //       default:
    //         alert(res.errmsg)
    //     }
    //   } catch (e) {
    //     alert('获取优惠券失败，请重试！')
    //   } finally {
    //     this.busy = false
    //   }
    // },
    loginSucc() {
      this.getCoupon()
    }
  }
}
</script>
