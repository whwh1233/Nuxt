<style>
.m65 {
  padding: 20px 40px;
}
.user__box {
  width: 100%;
  height: 120px;
  border-radius: 40px;
  border: 1px solid #dddddd;
  padding: 0px 38px 0px 28px;
  display: flex;
  align-items: center;
  box-sizing: border-box;
}
.user__desc {
  flex: 1;
}
.user__icon {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  margin-right: 18px;
  background: #fff no-repeat center/contain;
}
.user__name {
  font-size: 28px;
  font-family: PingFangSC-Medium;
  font-weight: 500;
  color: #000000;
}
.desc__detail {
  font-size: 24px;
  font-family: PingFangSC-Regular;
  font-weight: 400;
  color: #aaaaaa;
  margin-right: 10px;
}
.btn__focus {
  width: 84px;
  height: 44px;

  border-radius: 22px;
  text-align: center;
  box-sizing: border-box;
}
.btn__focus--no {
  border: 3px solid #000000;
  color: #000000;
  font-size: 24px;
  font-family: PingFangSC-Medium;
  font-weight: 500;
  line-height: 38px;
}
.btn__focus--yes {
  border: 1px solid #dddddd;
  color: #555555;
  font-size: 20px;
  font-family: PingFangSC-Medium;
  font-weight: 500;
  line-height: 42px;
}
</style>

<template>
  <div class="m65">
    <navigator :url="user.jumpUrl" class="user__box bgc-wt" v-for="(user, index) in tplData.userList" :key="index">
      <div class="user__icon" :style="{ backgroundImage: 'url(' + user.faceUrl + ')' }"></div>
      <div class="user__desc">
        <p class="user__name">{{ user.nick }}</p>
        <p class="desc__detail line line-1" v-if="user.goodAtList.length > 0">
          擅长种草<template v-for="good in user.goodAtList">{{ good }}</template>
        </p>
      </div>
      <div class="btn__focus" @click.stop="focus(user)" :class="user.relation === 0 ? 'btn__focus--no' : 'btn__focus--yes'">
        {{ user.relation === 0 ? '关注' : '已关注' }}
      </div>
    </navigator>
    <!-- <login ref="login" @login-succ="loginSucc"></login> -->
  </div>
</template>

<script>
// import API from 'api/api'
// import login from 'components/login/login'
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
    loginComp() {
      return this.$refs.login
    }
  },
  methods: {
    async focus(user) {
      let userId = user.userId
      let res
      if (user.relation === 0) {
        res = await this.request.post(API.followUser, { userId })
      } else {
        res = await this.request.post(API.unFollowUser, { userId })
      }
      res = res.data
      if (res.errno === 0) {
        return this.$set(user, 'relation', user.relation === 0 ? 1 : 0)
      } else {
        if (res.errno === 201) {
          this.loginComp.login(window.location.href)
        } else {
          alert('网络错误,请重试')
        }
      }
    }
  },
  components: {
    // login
  },
  data() {
    return {}
  }
}
</script>
