<style scoped>
.m63 {
  padding: 0 40px;
}

.m63__ipt {
  display: block;
  padding: 0 20px;
  width: 100%;
  height: 82px;
  font-size: 32px;
  line-height: 80px;
  box-sizing: border-box;
  border: 1px solid #eee;
  background: #fff;
}

.m63__btn {
  margin-top: 20px;
  height: 80px;
  color: #fff;
  font-size: 30px;
  line-height: 80px;
  text-align: center;
  background: #f95555;
}
</style>

<template>
  <div class="m63 cfix">
    <input v-model="mobile" type="tel" maxlength="11" class="m63__ipt" placeholder="请填写会员账户手机号" />
    <div class="m63__btn" @click="submitForm">预约</div>
  </div>
</template>

<script>
// import API from 'api/api'
const mobileReg = /^1\d{10}$/

export default {
  data() {
    return {
      mobile: '',
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
  methods: {
    async submitForm() {
      if (this.busy) return
      if (!this.mobile) {
        return alert('请填写手机号')
      }
      if (!mobileReg.test(this.mobile)) {
        return alert('请输入正确的手机号')
      }
      this.busy = true
      let res = await this.request.post(API.addReservation, {
        targetId: this.tplData.appointmentId,
        mobile: this.mobile
      })
      res = res.data
      if (res.errno !== 0) {
        return alert(res.errmsg)
      }
      let data = res.data
      alert(data.result)
    }
  }
}
</script>
