<style>
.m29__container {
  display: flex;
  align-items: center;
  margin: 20px auto;
  width: 66.66667%;
  height: 120px;
  border-radius: 10px;
  background: rgba(0, 0, 0, 0.75);
}

.m29__img {
  display: block;
  margin-left: 10px;
  width: 70px;
  height: 100px;
  border-radius: 5px;
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.m29__rest {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin-left: 20px;
  margin-right: 10px;
  height: 84px;
  overflow: hidden;
}

.m29__text {
  width: 100%;
  color: #fff;
  font-size: 24px;
  line-height: 1;
}

.m29__text--rd {
  color: #ff4d4d;
}

.m29__flex {
  display: flex;
}

.m29__user,
.m29__brand {
  display: block;
  margin: 0 5px;
  color: #999;
}

.m29__user {
  margin-left: 0;
}

.m29__arrow {
  display: block;
  margin-right: 20px;
  width: 24px;
  height: 24px;
}
</style>

<template>
  <top-notice :show="!!notice">
    <a @click.stop="link" class="m29__container">
      <div class="m29__img" :style="notice ? 'background-image:url(' + notice.itemPic + ')' : ''"></div>
      <div class="m29__rest">
        <p class="m29__text m29__flex">
          <span class="m29__user truncate">{{ notice ? notice.nick : '' }}</span>
          {{ notice ? '将' : '' }}
          <span class="m29__brand truncate">{{ notice ? notice.brandName : '' }}</span>
          {{ notice ? '的' : '' }}
        </p>
        <p class="m29__text m29__text--rd truncate">{{ notice ? notice.itemName : '' }}</p>
        <p class="m29__text">{{ notice ? '加入了购物车' : '' }}</p>
      </div>
      <i class="bi bi-arr-r-wt m29__arrow"></i>
    </a>
  </top-notice>
</template>

<script>
// import TopNotice from 'components/notice/top-notice'

export default {
  data() {
    return {
      notice: null,
      topNoticeTop: ''
    }
  },
  props: {
    tplData: {
      type: Object,
      default: () => {}
    }
  },
  computed: {
    cartList() {
      return this.tplData.cartList
    }
  },
  components: {
    // TopNotice
  },
  methods: {
    link() {
      if (!this.notice) return
      let _uri
      if (this.isApp) {
        _uri = 'openvc://?vc=sellitemvc&itemid=' + this.notice.itemId
      } else {
        _uri = '/m/uiww/getsellitem?itemId=' + this.notice.itemId
      }
      this.navTo(_uri)
    }
  },
  mounted() {
    let i = 0
    let showNotice = () => {
      if (++i === this.cartList.length) {
        i = 0
      }
      this.notice = this.cartList[i]
      setTimeout(() => {
        this.notice = null
      }, 2500)
    }
    setInterval(() => {
      showNotice()
    }, 6500)
    showNotice()
  }
}
</script>
